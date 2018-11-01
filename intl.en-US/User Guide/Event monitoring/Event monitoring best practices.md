# Event monitoring best practices {#concept_hpq_3jb_wdb .concept}

## Use cases {#section_b4b_pjk_zdb .section}

Exceptions may occur when the service is running. Some exceptions can be automatically restored by retry and other methods, while the others cannot. Serious exceptions can even lead to customer business interruption.  Therefore, a system is necessary to record these exceptions and trigger alarms when specific conditions are met. The traditional method is to print file logs and collect the logs to specific systems, for example, open-source ELK \(ElasticSearch,  Logstash, and Kibana\).   These open-source systems consist of multiple complex distributed systems. The complicated technology and high cost make independent maintenance challenging.  CloudMonitor provides the event monitoring feature to effectively solve these problems.

The following examples explain how to use the event monitoring feature.

## Case studies {#section_ehq_qjk_zdb .section}

1.  Report exceptions

    Event monitoring provides two methods for data reporting, namely, JAVA SDK and OpenAPI. The following describes how to report data by using JAVA SDK.

    1.  Add Maven dependency

        ```
        <dependency>
            <groupId>com.aliyun.openservices</groupId>
            <artifactId>aliyun-cms</artifactId>
            <version>0.1.2</version>
        </dependency>
        ```

    2.  Initialize SDK

        ```
        // Here, 118 is the application grouping ID of CloudMonitor. Events can be categorized by applications. You can view group IDs in CloudMonitor application grouping list.
        CMSClientInit.groupId = 118L;
        // The address is the reporting entry of the event system, which is currently the public network address.  AccessKey and Secret/key are used for personal identity verification.
        CMSClient c = new CMSClient("https://metrichub-cms-cn-hangzhou.aliyuncs.com", accesskey, secretkey);
        ```

    3.  Determine whether to asynchronously report the data.

        CloudMonitor event monitoring provides synchronous reporting policy by default. The good thing is that writing code is simple, and the reported events are reliable and free from data loss.

        However, such policy also brings some problems as well.  Event reporting codes are embedded in business codes, which may block code running and affect the normal business in case of network fluctuations. Many business scenarios do not require events to be 100% reliable, so a simple asynchronous reporting encapsulation is sufficient. Write the event into a LinkedBlockingQueue and perform batch reporting on the backend asynchronously using ScheduledExecutorService.

        ```
        //Initialize queue and Executors:
        private LinkedBlockingQueue<EventEntry> eventQueue = new LinkedBlockingQueue<EventEntry>(10000);
        private ScheduledExecutorService schedule = Executors.newSingleThreadScheduledExecutor();
        // Report event:
        //Every event contains its name and content. The name is for identification and the content contains details of the event, in which the full-text search is supported.
        public void put(String name, String content) {
            EventEntry event = new EventEntry(name, content);
             // When the event queue is full, additional events are discarded directly. You can adjust this policy as needed.
            boolean b = eventQueue.offer(event);
            if (! b) {
                logger.warn("The event queue is full, discard: {}", event);
            }
        
        //Submit events asynchronously. Initialize scheduled tasks. Report events in batch by run every second.  You can adjust the reporting interval as needed.
        schedule.scheduleAtFixedRate(this, 1, 1, TimeUnit.SECONDS);
        public void run() {
            do {
                batchPut();
            } while (this.eventQueue.size() > 500);
        
        private void batchPut() {
            // Extract 99 events from the queue for batch reporting.
            List<CustomEvent> events = new ArrayList<CustomEvent>();
            for (int i = 0; i < 99; i++) {
                EventEntry e = this.eventQueue.poll();
                if (e == null) {
                    break;
                
                events.add(CustomEvent.builder().setContent(e.getContent()).setName(e.getName()).build());
            
            if (events.isEmpty()) {
                return;
            
             // Report events in batch to CloudMonitor. No retry or retry in SDK is added here. If you have high requirement for event reliability, add retry policies.
            try {
                CustomEventUploadRequestBuilder builder = CustomEventUploadRequest.builder();
                builder.setEventList(events);
                CustomEventUploadResponse response = cmsClient.putCustomEvent(builder.build());
                if (!" 200".equals(response.getErrorCode())) {
                    logger.warn("event reporting error: msg: {}, rid: {}", response.getErrorMsg(), response.getRequestId());
                
            } catch (Exception e1) {
                 logger.error("event reporting exception", e1);
            
        
        ```

    4.  Event reporting demo
        -   Demo1：http Controller exception monitoring

            The main purpose is to monitor if a large number of exceptions exist in HTTP requests. If the number of exceptions per minute exceeds a certain limit, an alarm is triggered. The implementation principle is to intercept HTTP requests by using Spring interceptor, servlet   filter and other technologies. Logs are created in case of exceptions and alarms are triggered by setting alarm rules.

            The event reporting demo is as follows:

            ```
            // Each event should be informative for searching and locating. Here, map is used for organizing events and converted to Json format as event content.  
            Map<String, String> eventContent = new HashMap<String, String>();
            eventContent.put("method", "GET"); // http request method
            eventContent.put("path", "/users"); // http path
            eventContent.put("exception", e.getClass().getName()); //Exception class name for searching
            eventContent.put("error", e.getMessage()); // Error message of exception
            eventContent.put("stack_trace", ExceptionUtils.getStackTrace(e)); // Exception stack for locating
            // Finally submit the events in the preceding asynchronous reporting method. Since no retry is performed in asynchronous reporting, event loss of small probability may happen. However, it is sufficient for alarms of unknown http exceptions.
            put("http_error", JsonUtils.toJson(eventContent));
            image.png](http://ata2-img.cn-hangzhou.img-pub.aliyun-inc.com/864cf095977cf61bd340dd1461a0247c.png)
            ```

        -   Demo2: Monitoring of scheduled tasks on the backend and message consumption

            Like the preceding http events, many similar business scenarios require alarms. In the business scenarios such as backend tasks and message queue consumption, the events can be reported by using similar methods to achieve effective monitoring.  When any exception occurs, alarms are triggered immediately.

            ```
            //Event organization of the message queue:
            Map<String, String> eventContent = new HashMap<String, String>();
            eventContent.put("cid", consumerId); // Consumer ID
            eventContent.put("mid", msg.getMsgId()); // Message ID
            eventContent.put("topic", msg.getTopic()); // Message topic
            eventContent.put("body", body); // Message body
            eventContent.put("reconsume_times", String.valueOf(msg.getReconsumeTimes())); // The number of retries after message failure
            eventContent.put("exception", e.getClass().getName()); //Exception class name in case of exception
            eventContent.put("error", e.getMessage()); // Exception message
            eventContent.put("stack_trace", ExceptionUtils.getStackTrace(e)); // Exception stack
            // Finally, report the event
            put("metaq_error", JsonUtils.toJson(eventContent));
            ```

            Check the event after reporting:

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6166/154106067121440_en-US.png)

        -   Set alarms for queue message consumption exceptions:

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6166/154106067121441_en-US.png)

        -   Demo 3: Record important events

            Another use case of events is to record important actions for later check without sending alarms.  For example, operation logs for important business, password change/order change, remote logon, and so on.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6166/154106067121442_en-US.png)


