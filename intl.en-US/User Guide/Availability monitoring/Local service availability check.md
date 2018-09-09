# Local service availability check {#concept_d4j_rvf_vdb .concept}

Following are the guidelines that will help you to monitor the availability of local service processes and send alarms when the service response lapses or returns an error code.

**Note:** 

-   This function requires the CloudMonitor agent to work appropriately. Hence, ensure that CloudMonitor agent is preinstalled on the relevant machines.
-   An availability test is performed every minute.
-   Before using this function, [create application groups](intl.en-US/User Guide/Application Groups/Create application groups.md#).

## Procedure {#section_ost_4bg_vdb .section}

1.  In the [CloudMonitor console](https://cms.console.aliyun.com/?spm=a2c4g.11186623.2.5.6tg2Gb#/home/ecs), select **Application Groups** from the left-side navigation pane.
2.  Select the target application group and click **Group Name** to go to the application group details page.
3.  Select **Availability Monitoring** from the left-side navigation pane.
4.  Click **Create Configuration** in the upper-right corner of the page. The **Create Local Health Check** dialog box is displayed.

    **Monitoring Configurations** area:

    -   Target Server: This is the machine that initiates the test. The local service availability monitoring test source and test target are the same machine.
    -   Detection Type: Select URL or IP address.
    -   Detection Target: The syntax of HTTP\(S\) is localhost:port/path and that of **TELNET** is 127.0.0.1:port. For example, to test whether Tomcat is responsive, selectHTTP\(S\) and enter localhost:8080/monitor; to test MySQL connectivity, select TELNET and enter 127.0.0.1:3306.
    **Alarm Configuration** area:

    Alarms can be configured by status code or  response time. An alarm is triggered when the returned status code is the same as the setting or no response is returned after the predefined timeout threshold has lapsed. The alarm notification will be sent to the contact group associated with the application group. For local availability monitoring, set the status code setting to greater than 400.

    -   **Status code**: An alarm is triggered when the returned status code is the same as the setting.
    -   **Notification method**: It is the method by which alarm notifications are sent.
    -   **Advanced Configuration**
        -   Muted For: the period of time after which an alarm is sent again if the exception persists after the alarm is triggered. 
        -   Effective From: the time when an alarm rule becomes effective. You can configure this parameter based on your actual needs.
5.  Click **OK** to save the configurations. A local service availability monitoring task has been created successfully. If your service does not respond, a message or an email will be sent to you and the number of abnormal instances will be displayed in the list. Then, click the **number of exceptions** to view details about the abnormal instances.
6.  Click the **number of abnormal machines** to view details about the abnormal machines.

