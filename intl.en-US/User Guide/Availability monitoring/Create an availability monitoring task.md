# Create an availability monitoring task {#concept_bzk_w3l_ngb .concept}

This topic describes how to configure availability monitoring so that you can receive alarms if a local service or a dependent remote service does not respond within a specified timeout period or returns an error status code.

## Background {#section_xnx_z3l_ngb .section}

Based on availability monitoring, CloudMonitor helps you quickly locate issues when a local service or a remote service has no response. CloudMonitor can send an alarm to you if the local service or the remote service fails to respond within a specified timeout period or returns an error status code. In this way, you can efficiently check response conditions of local or remote paths and ports.

## Prerequisites {#section_gkm_gll_ngb .section}

-   You have created a resource group for availability monitoring. For more information, see [Create application groups](reseller.en-US/User Guide/Application groups/Create application groups.md#).
-   You have installed the CloudMonitor agent on the monitored host. For more information, see[Introduction to the CloudMonitor GoLang agent](reseller.en-US/User Guide/Host monitoring/Introduction to the CloudMonitor GoLang agent.md#).

## Procedure {#section_lyf_x4f_vdb .section}

 **Restrictions** 

**Note:** 

-   Availability monitoring depends on the CloudMonitor agent. Make sure that you have installed the CloudMonitor agent on the monitored host.
-   CloudMonitor performs the availability detection once a minute.

 **Procedure** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Application Groups** to go to the Application Groups page.
3.  Click the name of the application group where you want to create an availability monitoring task to go to the Basic Information page of the application group.
4.  In the left-side navigation pane, click **Availability Monitoring** to go to the Availability Monitoring page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115387/156160734537788_en-US.png)

5.  Click **Create Configuration** in the upper-right corner to go to the Create Availability Monitoring page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115387/156160734537790_en-US.png)

6.  Set Task Name and Target Server. You can configure the same detection rule for all hosts in the group or some hosts in the group.
7.  Set Detection Type to **URL or IP Address**, **ApsaraDB for RDS**, or **ApsaraDB for Redis**. Afterward, set Detection Target.
    -   If you set Detection Type to **URL or IP Address**, you can set Detection Target to **HTTP\(S\)**, **TELNET**, or **PING**. If you set Detection Target to **HTTP\(S\)**, you can set Request Method to **HEAD**, **GET**, or **POST**. You can also configure the returned value.
    -   If you set Detection Target to **ApsaraDB for RDS** or **ApsaraDB for Redis**, you can view the instances in your group and their connection addresses.
8.  In the Alarm Configuration field, set the Status Code and Response Time metrics. CloudMonitor generates an alarm if either of these metrics reaches the specified threshold. The system sends alarms to the contact group of the corresponding application group.
    -   **Status Code**: the system generates an alarm if the local or remote service returns a status code as specified.
    -   **Response Time**: the system generates an alarm if the local or remote service failed to respond within the specified timeout period.
    -   **Notification Method**: the method that the system uses to send alarms.
    -   **Advanced Configuration**: you can configure **Mute For** and **Effective Period**.
        -   **Mute For** is a period when your alarm rules are muted so that the system does not send any alarms even when the local or remote service runs in the specified alarm conditions.
        -   **Effective Period**: the time when an alarm rule takes effect. The system only sends alarms within the effective period according to the alarm rule. The system only records alarms if the alarms occur during a non-effective period.
9.  Click **OK**.

