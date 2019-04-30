# Create an availability monitoring task {#concept_bzk_w3l_ngb .concept}

This topic describes how to create availability monitoring tasks to quickly identify situations where local or dependent remote services are unresponsive.

## Background information {#section_xnx_z3l_ngb .section}

CloudMonitor availability monitoring helps you quickly identify situations where local or remote hosts are unresponsive. Alerts are sent if the service does not respond within the specified timeout period or when an error status code is returned.

## Prerequisites {#section_gkm_gll_ngb .section}

-   A group is created for the resources for availability monitoring. For more information, see [Create application groups](reseller.en-US/User Guide/Application groups/Create application groups.md#).
-   The CloudMonitor agent is installed for the monitored host. For more information, see [Introduction to the CloudMonitor GoLang agent](reseller.en-US/User Guide/Host monitoring/Introduction to the CloudMonitor GoLang agent.md#).

## Procedure {#section_lyf_x4f_vdb .section}

**Precautions**

**Note:** 

-   Availability monitoring depends on the CloudMonitor agent. Ensure that the CloudMonitor agent has been installed on the monitored host.
-   Monitoring is performed once a minute.

**Procedure**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Application Groups**. The Application Groups page is displayed.
3.  Click the name of the application group for which an availability monitoring task is to be created. The application group details page is displayed.
4.  In the left-side navigation pane, click **Availability Monitoring**. The Availability Monitoring page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115387/155661014037788_en-US.png)

5.  Click **Create Configuration** in the upper-right corner. The Create Availability Monitoring page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115387/155661014037790_en-US.png)

6.  Set Task Name and Target Server. You can configure the same detection rule to be applied to all hosts in the group or just a portion of hosts in the group.
7.  Set Detection Type to **URL or IP Address**, **ApsaraDB for RDS**, or **ApsaraDB RDS for Redis**. Set Detection Target.
    -   If you set Detection Type to **URL or IP Address**, you can set Detection Target to **HTTP\(S\)**, **TELNET**, or **PING**. If you set Detection Target to **HTTP\(S\)**, you can set Request Method to **HEAD**, **GET**, or **POST**. You can also configure the returned value.
    -   If you set Detection Target to **ApsaraDB for RDS** or **ApsaraDB RDS for Redis**, the related instances in your group and their access addresses are displayed.
8.  In the Alert Configuration section, set Status Code and Response Time. An alert is triggered if the conditions of either parameter are met. Alerts are sent to the contact group of the corresponding application group.
    -   **Status Code**: An alert is triggered if the returned status code meets the conditions set in the alert rule.
    -   **Response Time**: An alert is triggered if the response time meets the conditions set in the alert rule.
    -   **Notification Method**: the method by which alerts are sent.
    -   **Advanced Configuration**: You can configure **Muted For** and **Effective From**. **Muted For** is a period when your alert rules are muted so that no alerts are sent even if the conditions specified in your alert rules are met. **Effective From** is a period when the alert rules are effective. Alerts are sent if the conditions specified in your alert rules are met during this period.
9.  Click **OK**.

