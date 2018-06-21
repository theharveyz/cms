# Local health check {#concept_d4j_rvf_vdb .concept}

Following are the guidelines that will help you to monitor the availability of local service processes and send alarms when the service response lapses or returns an error code.

**Note:** 

-   This function requires the CloudMonitor agent to work appropriately. Hence, ensure that CloudMonitor agent is preinstalled on the relevant machines.
-   An availability test is performed every minute.
-   Before using this function, [Create application groups](intl.en-US/User Guide/Application Groups/Create application groups.md#).

## Procedure {#section_ost_4bg_vdb .section}

1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/?spm=a2c4g.11186623.2.5.6tg2Gb#/home/ecs), select Application Groups from the left-side navigation pane to go to the Application Groups page.
2.  Select the application group for which you want to create a local service availability monitoring task, and click the Group Name to go to the application group details page.
3.  Select **Availability Monitoring** from the left-side navigation pane to go to the Availability Monitoring page.
4.  Click Create Configuration in the upper-right corner of the page to go to the Create Local Health Check page.
5.  Select a test source: This is the machine that initiates the test. The local service availability monitoring test source and test target are the same machine.
6.  Select test type: Select URL or IP.
7.  Test target：forHTTP, the syntax is localhost:port/path，for **Telnet**,  the syntax is 127.0.0.1:port  For instance, if you want to test MySQL connectivity, select Telnet and then enter 127.0.0.1:3306. To test whether or not Tomcat is responsive, selectHTTP and then enter localhost:8080/monitor.
8.  Select an Alarm Configuration. Alarms can be configured by status code or  response time. An alarm is triggered when the returned status code is the same as the setting or no response is returned after the predefined timeout threshold has lapsed. The alarm notification will be sent to the contact group associated with the application group.  For local availability monitoring, set the status code setting to greater than 400.
    -   **Status code alarm**: An alarm is triggered when the returned status code is the same as the setting.
    -   **Notification method**: It is the method by which alarm notifications are sent.
    -   **Advanced Configuration**
        -   Channel silence time:  the period of time after which an alarm is sent again if the exception persists after the alarm is triggered. 
        -    Effective time : the time when an alarm policy becomes effective. You can configure these options based on your actual needs.
    -   ![](images/2214_en-US.png)

9.  You will have a local service availability monitoring task created successfully, once you create and save the above configurations. When your service does not respond, it will send a message, email and other alarm notifications, the number of instances of the alarm is displayed in the list, and click the **number of exceptions** to view the exception instance details.

    ![](images/1901_en-US.png)

10. Click the number of abnormal machines to detect them to display the exception machine details.

    ![](images/2218_en-US.png)


