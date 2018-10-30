# Manage alarm rules {#concept_evg_4sm_vdb .concept}

The alarm service provides monitoring alarm capability to help you know abnormal metric data and troubleshoot faults in a timely manner.

## ​Parameter description​ {#section_z4b_ktm_vdb .section}

-   Products: host monitoring, RDS, OSS, and others
-   Resource Range: range of the alarm rule. There are three resource ranges: **All Resources**, **Application Group** and **Instances**. When you set **Resource Range** to **All Resources**, the maximum number of resources that can report alarms is 1000. If the resources is more than 1000, some resources cannot report alarms even when they exceed the threshold. It is recommended that you use application groups to divide resources by service before setting up alarm rules.
    -   All Resources: indicates that the alarm rule applies to all instances of the product under the user name. For example, if you set the resource range to all resources, and set the alarm threshold for MongoDB CPU usage to 80%, the alarm rule is hit when the CPU usage of a MongoDB instance under your username is greater than 80%.

    -   Application Group: indicates that the rule applies to all instances under an application group. For example, if you set the resource range to application group, and set the alarm threshold for host CPU usage to 80%, the alarm rule is hit when the CPU usage of a host instance under your username is greater than 80%.

    -   Instances: indicates that the rule only applies to a specific instance. For example, if you set the resource range to instances, and set the alarm threshold for host CPU usage to 80%, the alarm rule is hit when the CPU usage of the specified instance is greater than 80%.

-   Rule name: name of the alarm rule.

-   Rule Description: Body of the alarm rule, defining the alarm-triggering conditions for metric data. For example, if you describe the rule as "1-minute average CPU usage \>=90%", the alarm service checks every minute whether the average value of metric data within one minute is greater than or equal to 90%.

    **Alarm rules example**: In host monitoring, for example, a single server metric item reports one data point in 15 seconds, and 20 data points in 5 minutes.

    -   5-minute average CPU usage \> 90% indicates that the average value of the 20 data points about CPU usage in 5 minutes is greater than 90%.
    -   5-minute CPU usage always \> 90% indicates that the values of the 20 data points about CPU usage in 5 minutes are all greater than 90%.

    -   5-minute CPU usage once \> 90% indicates that the value of at least one of the 20 data points about CPU usage in 5 minutes is greater than 90%.

    -   Total 5-minute Internet outbound traffic \> 50 MB indicates that the sum of the values of the 20 data points about Internet outbound traffic in 5 minutes is greater than 50 MB.

-   **Alarm after the threshold value is exceeded multiple times consecutively**: An alarm notification will be sent if the detected values meet the alarm rule multiple times consecutively.

-   **Effective time**: time when an alarm rule takes effect. The alarm service checks metric data and determines whether to generate an alarm only when the alarm rule is effective.

-   **Notification object**: a group of contacts who receive alarm notifications.

-   **Alarm level**: it is divided into three levels: Critical, Warning, and Info. Different levels have different notification methods.

    -   Critical: voice call + mobile phone SMS + email + DingTalk Robot
    -   Warning: SMS + email + DingTalk Robot
    -   Info: email + DingTalk Robot
-   **Email remarks**: supplementary information customized for an alarm email. The remarks are sent together with the alarm notification email.


## Manage alarm rules {#section_zyz_szm_vdb .section}

CloudMonitor provides three alarm rule management portals: application group page, metric item list page, and alarm rule list page of the alarm service.

-   [Manage alarm rules](https://help.aliyun.com/document_detail/45246.html?spm=a2c4g.11186623.2.6.7RGVZL) in application groups.

-   [Manage alarm rules](https://help.aliyun.com/document_detail/48184.html?spm=a2c4g.11186623.2.7.7RGVZL) in host monitoring.

-   [Manage alarm rules](https://help.aliyun.com/document_detail/28585.html?spm=a2c4g.11186623.2.8.7RGVZL) in cloud service monitoring.

-   [Use alarm rules](https://help.aliyun.com/document_detail/28600.html?spm=a2c4g.11186623.2.9.7RGVZL) in site monitoring.

-   [Manage alarm rules](https://help.aliyun.com/document_detail/28605.html?spm=a2c4g.11186623.2.10.7RGVZL) in custom monitoring.


