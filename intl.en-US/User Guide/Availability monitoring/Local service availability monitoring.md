# Local service availability monitoring {#concept_d4j_rvf_vdb .concept}

This topic describes how to configure local service availability monitoring so that you can receive alert notification if the service does not respond within a specified timeout period or when an error status code is returned.

## Background information {#section_xnx_z3l_ngb .section}

Local service availability monitoring sends alert notification to identify situations where local services are unresponsive or when an error status code is returned.

## Prerequisites {#section_ost_4bg_vdb .section}

-   Local service availability monitoring depends on the CloudMonitor agent. Ensure that the CloudMonitor agent has been installed on the monitored host. For more information, see [Introduction to the CloudMonitor GoLang agent](reseller.en-US/User Guide/Host monitoring/Introduction to the CloudMonitor GoLang agent.md#).
-   Before you use local service availability monitoring, you must [Create application groups](reseller.en-US/User Guide/Application groups/Create application groups.md#).

## Procedure {#section_py5_zk5_xgb .section}

**Precautions**

**Note:** 

-   Local service availability monitoring depends on the CloudMonitor agent to run properly. Ensure that the CloudMonitor agent has been installed on the monitored host.
-   An availability test is performed once a minute.

**Procedure**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Application Groups**. The Application Groups page is displayed.
3.  Click the name of the application group for which you want to create a local service availability monitoring task. The application group details page is displayed.
4.  In the left-side navigation pane, click **Availability Monitoring**. The Availability Monitoring page is displayed.
5.  Click **Create Configuration** in the upper-right corner. The Create Availability Monitoring page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6170/155661026739724_en-US.png)

6.  Set Task Name and Target Server. You can configure the same detection rule to be applied to all hosts in the group or just a portion of hosts in the group.
7.  Set Detection Type to **URL or IP Address**, **ApsaraDB for RDS**, or **ApsaraDB RDS for Redis**. Set Detection Target.
8.  In the Alert Configuration section, set Status Code and Response Time. An alert is triggered if the conditions of either parameter are met. Alerts are sent to the contact group of the corresponding application group.
9.  Click **OK**. If your service does not respond within the timeout period, you will receive alert notification through text messages, emails, or other channels.
10. \(Optional\) The availability monitoring list displays the number of unhealthy hosts. Click **Unhealthy Hosts** to view the details of the abnormal hosts.

**Parameter description**

-   **Monitoring Configuration** section:
    -   **Target Server**: the host that initiates the test. Target Server and Detection Target are the same host.
    -   **Detection Type**: Select URL or IP Address.
    -   **Detection Target**: If you select HTTP\(S\), enter the target address in the format of `localhost:port/path`. If you select TELNET, enter the target address in the format of `127.0.0.1:port`. For example, to test whether Tomcat responds normally, select HTTP\(S\) and enter `localhost:8080/monitor`. To test the connectivity of MySQL, select TELNET and enter `127.0.0.1: 3306`.

-   **Alarm Configuration** section:

    Both **Status Code** and **Response Time** are used as the metrics of availability monitoring. An alert is triggered if either metric value reaches the specified threshold. Alerts are sent to the contact group of the corresponding application group. For local availability monitoring, set the status code greater than 400.

    -   **Status Code**: An alert is triggered if the returned status code meets the conditions set in the alert rule.
    -   **Notification Method**: the method by which alerts are sent.
    -   **Advanced Configuration**:
        -   **Muted For**: a period when your alert rules are muted so that no alerts are sent even if the conditions specified in your alert rules are met.
        -   **Effective From**: a period when the alert rules are effective. Alerts are sent if the conditions specified in your alert rules are met during this period. You can configure these parameters based on your actual needs.

