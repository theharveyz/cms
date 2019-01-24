# Server Load Balancer {#concept_by4_yqt_xdb .concept}

By monitoring multiple metrics from Server Load Balancer \(SLB\), including inbound and outbound traffic and the number of data packets and connections, CloudMonitor helps you to monitor the running status of instances and configure alarm rules accordingly. CloudMonitor automatically collects data from SLB from the time after you create an SLB instance.

## Monitoring service {#section_kbm_drt_xdb .section}

-   Metrics
    -   Layer-4 metrics

        |Metric|Description|Dimension|Unit|Minimum monitoring frequency|
        |:-----|:----------|:--------|:---|:---------------------------|
        |Port inbound traffic|The traffic consumption for accessing a specified SLB port from the Internet|Port|bit/s|1 minute|
        |Port outbound traffic|The traffic consumption for accessing the Internet from a specified SLB port|Port|bit/s|1 minute|
        |Number of inbound data packets by port|The number of the request packets \(per second\) that a specified SLB port receives|Port|count/s|1 minute|
        |Number of outbound data packets by port|The number of the request packets \(per second\) that a specified SLB port sends|Port|count/s|1 minute|
        |Number of new port connections|The average number of times \(per second\) the first SYN\_SENT status occurs in a TCP three-way handshake during a statistical period|Port|count/s|1 minute|
        |Number of active port connections|The number of connections in ESTABLISHED status during a statistical period|Port|count|1 minute|
        |Number of inactive port connections|The number of all TCP connections except the connections in ESTABLISHED status during a statistical period|Port|count|1 minute|
        |Number of concurrent port connections|The total number of connections|Port|count|1 minute|
        |Number of backend healthy ECS instances by port|The number of healthy instances reported by a health check|Port|count|1 minute|
        |Number of backend unhealthy ECS instances by port|The number of unhealthy instances reported by a health check|Port|count|1 minute|
        |Number of discarded port connections|The average number of connections discarded per second|Port|count/s|1 minute|
        |Number of discarded inbound data packets by port|The average number of inbound packets discarded per second|Port|count/s|1 minute|
        |Number of discarded outbound data packets by port|The average number of outbound packets discarded per second|Port|count/s|1 minute|
        |Number of discarded inbound bandwidth by port|The average inbound traffic discarded per second|Port|bit/s|1 minute|
        |Number of discarded outbound bandwidth by port|The average outbound traffic discarded per second|Port|bit/s|1 minute|
        |Number of active instance connections|The number of connections in ESTABLISHED status during a statistical period|Instance|count/s|1 minute|
        |Number of inactive instance connections|The number of connections except those in ESTABLISHED status during a statistical period|Instance|count/s|1 minute|
        |Number of discarded instance connections|The number of connections discarded per second|Instance|count/s|1 minute|
        |Number of discarded inbound data packets by instance|The number of inbound packets discarded per second|Instance|count/s|1 minute|
        |Number of discarded outbound data packets by instance|The number of outbound packets discarded per second|Instance|count/s|1 minute|
        |Discarded inbound bandwidth by instance|The amount of inbound traffic discarded per second|Instance|bit/s|1 minute|
        |Discarded outbound bandwidth by instance|The amount of outbound traffic discarded per second|Instance|bit/s|1 minute|
        |Number of concurrent instance connections|The total number of connections of the instance \(the sum of active and inactive connections\)|Instance|count/s|1 minute|
        |Number of new instance connections|The average number of times \(per second\) the first SYN\_SENT status occurs in a TCP three-way handshake during a statistical period|Instance|count/s|1 minute|
        |Number of inbound data packets by instance|The number of request packets received per second|Instance|count/s|1 minute|
        |Number of outbound data packets by instance|The number of packets sent per second|Instance|count/s|1 minute|
        |Number of inbound bandwidth by instance|The traffic consumption for accessing the SLB instance from the Internet|Instance|bit/s|1 minute|
        |Number of outbound bandwidth by instance|The traffic consumption for accessing the Internet from the SLB instance|Instance|bit/s|1 minute|

    -   Layer-7 metrics

        |Metric|Description|Dimension|Unit|Minimum monitoring frequency|
        |:-----|:----------|:--------|:---|:---------------------------|
        |Port QPS|The QPS of a specified port|Port|count/s|1 minute|
        |Port RT|The average request latency of a specified port|Port|ms|1 minute|
        |Status codes of the format 2xx|The number of status codes of the format 2xx that SLB returns to the client|Port|count/s|1 minute|
        |Status codes of the format 3xx|The number of status codes of the format 3xx that SLB returns to the client|Port|count/s|1 minute|
        |Status codes of the format 4xx|The number of status codes of the format 4xx that SLB returns to the client|Port|count/s|1 minute|
        |Status codes of the format 5xx|The number of status codes of the format 5xx that SLB returns to the client|Port|count/s|1 minute|
        |Other status codes|The number of other status codes that SLB returns to the client|Port|count/s|1 minute|
        |Upstream status codes of the format 4xx|The number of status codes of the format 4xx that RS returns to SLB|Port|count/s|1 minute|
        |Upstream status codes of the format 5xx|The number of status codes of the format 5xx that RS returns to the client|Port|count/s|1 minute|
        |Upstream RT|The average request delay from RS to proxy|Port|ms|1 minute|
        |Instance QPS|The QPS of an instance|Instance|count/s|1 minute|
        |Instance RT|The average request latency of the instance|Instance|count/s|1 minute|
        |Status codes of the format 2xx|The number of status codes of the format 2xx that SLB returns to the client|Instance|count/s|1 minute|
        |Status codes of the format 3xx|The number of status codes of the format 3xx that SLB returns to the client|Instance|count/s|1 minute|
        |Status codes of the format 4xx|The number of status codes of the format 4xx that SLB returns to the client|Instance|count/s|1 minute|
        |Status codes of the format 5xx|The number of status codes of the format 5xx that SLB returns to the client|Instance|count/s|1 minute|
        |Other status codes|The number of status codes of other formats that SLB returns to the client|Instance|count/s|1 minute|
        |Upstream status codes of the format 4xx|The number of status codes of the format 4xx that RS returns to SLB|Instance|count/s|1 minute|
        |Upstream status codes of the format 5xx|The number of status codes of the format 5xx that RS returns to SLB|Instance|count/s|1 minute|
        |Upstream RT|The average request delay from RS to proxy|Instance|ms|1 minute|

        **Note:** The numbers of new connections, active connections, and inactive connections are all based on TCP connection requests from the client to SLB.

-   View monitoring data
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Server Load Balancer** to go to the SLB instance list page.
    3.  Select the region where the target instance is located and find the target instance.
    4.  Click the instance name or click **Monitoring Charts** in the **Actions** column.
    5.  On the Monitoring Charts tab page, you can view the monitoring data.
    6.  To switch to another chart view, click the chart view button in the upper-left corner of the page.

## ​Alarm service {#section_z4b_ktm_vdb .section}

-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are three alarm rule ranges available: **All Resources**, **Application Group**, and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all instances under a user name. For example, if you set the resource range to all resources, and set the alarm threshold for MongoDB CPU usage to 80%, then an alarm is triggered when the CPU usage of any MongoDB instance exceeds 80%. When you select **All Resources**, you can report an alarm for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Application Group**: Indicates that the specified rule applies to all instances under an application group. For example, if you set the resource range to **Application Group** and set the alarm threshold for host CPU usage to 80%, then an alarm is triggered when the CPU usage of any host in the corresponding application group exceeds 80%.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for host CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **1-minute average CPU usage \>=90%**, the alarm service will check every minute whether the average value of CPU usage within one minute meets or exceeds 90%.

        Consider the following example. For the alarm service in host monitoring, one data point is reported in 15 seconds for a single server metric, and 20 data points in five minutes. This relates to the following alarm rules.

        -   **5-minute average CPU usage \> 90%**: The average CPU usage value of the 20 data points in five minutes exceeds 90%.
        -   **5-minute CPU usage always \> 90%**: The CPU usage values of the 20 data points in five minutes all exceed 90%.
        -   **5-minute CPU usage once \> 90%**: The CPU usage value of at least one of the 20 data points in five minutes exceeds 90%.
        -   **Total 5-minute Internet outbound traffic \> 50 MB**: The sum of the outbound traffic values of the 20 data points in five minutes exceeds 50 MB.
    -   **Muted For**: the period of time that an alarm has been muted so that alarm contacts do not receive any alarm notifications during this period. An alarm rule can be muted up to 24 hours \(or 1 day\).
    -   **Triggered when threshold is exceeded for**: An alarm notification is sent if the detected values reach the alarm rule threshold a certain number of times consecutively.
    -   **Effective Period**: the period of time for which an alarm rule is effective. During this period of time, the alarm service checks metric data and determines whether to generate an alarm.
    -   **Notification Contact**: a group of contacts who receive alarm notifications.
    -   **Notification Methods**:
        -   Email and DingTalk chatbot
    -   **Email Subject**: The email subject is set as the product name, metric, and instance ID involved in the alarm by default.
    -   **Email Remark**: supplementary information customized for an alarm email. Remarks are sent as part of the alarm notification email.
    -    **HTTP CallBack**: Enter a URL accessible through the Internet and CloudMonitor will push the alarm information to the address through a POST request. Currently, only HTTP is supported.
-   **Set an alarm rule**
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Server Load Balancer** to go to the SLB instance list page.
    3.  Select the region to which the target instance belongs.
    4.  Find the target instance and click **Alarm Rules** in the **Actions** column.
    5.  On the Alarm Rules tab page, click **Create Alarm Rules** in the upper-right corner.
    6.  Set the parameters according to the preceding parameter descriptions and click **Confirm**.

