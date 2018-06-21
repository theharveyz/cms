# Manage alarm rules {#concept_evg_4sm_vdb .concept}

The alarm service is to provide monitoring and alarm capability for users on the cloud, helping you to know the monitoring data anomaly for the first time, deal with problems in a timely manner.

## Parameter descriptions {#section_z4b_ktm_vdb .section}

-   Products: such as host monitoring, RDS, OSS, etc.
-   Resource scope: the scope of action of the alarm rule. It is divided into three areas: all resources, application grouping and instance.
-   When a resource range is selected for all resources, the maximum number of resources that are reported is 1000, more than 1000 problems may occur that reach the threshold without warning, it is recommended that you use application grouping to divide resources by business before setting up alarms.

    -   All resources: indicates that the rule works on all instances of the corresponding product under the user name. For example, MongoDB with all the resource granularity set The CPU usage is greater than 80% alarm, as long as the MongoDB CPU usage is greater than 80% under the user, it hits this rule.

    -   Apply grouping: indicates that the rule works on all instances under an application grouping. For example, set the application grouping granularity of the host. The CPU usage is greater than 80% alarm, as long as there is a host CPU usage greater than 80% under this grouping, it hits this rule.

    -   Instance: indicates that the rule only works on a specific instance. For example, a host CPU with instance granularity is set. The usage rate is greater than 80% alarm, and only this instance of CPU usage is greater than 80% will hit this rule.

-   Rule name: the name of the alarm rule.

-   Rule Description: The body of the alarm rule that defines what conditions the monitoring data meets, trigger alarm rules. For example, the rule is described as a 1 minute average of CPU usage\> = 90, the alarm service checks once a minute if the data within 1 minute meets the average of\> = 90?

    Alarm rules example: Take host monitoring as an example, A single server monitoring indicator is reported to a data base for 15 seconds and 20 data points for 5 minutes.

    -   CPU usage is 5 minutes, with an average of\> 90, the meaning is that the average of 20 data points with CPU usage of 5 minutes is greater than 90.
    -   CPU usage is 5 minutes, always\> 90, the meaning is that the number of 20 data points with CPU usage of 5 minutes is all greater than 90.

    -   CPU usage for 5 minutes, as soon as one time\> 90, the meaning is that there are at least 1 Number of 20 data points with CPU usage of 5 minutes greater than 90.

    -   Public Network Flow flow of 5 minutes, total\> 50 m, the meaning is that the result of 20 data points sum for 5 minutes of public network flow is greater than 5 m.

-   Alarm after the threshold is exceeded several times in a row: After continuous detection, the results are in accordance with the description of the alarm rules to send alarm notifications.

-   Effective time: the effective time of the alarm rule, the alarm rule checks whether the monitoring data requires an alarm only during the effective time.

-   Notification object: the contact group that sent the alarm.

-   Alarm level: it is divided into critical, warning, info three levels, different levels correspond to different notification methods.

    -   Critical: phone voice + mobile phone SMS + mail + DingTalk Robot
    -   Warning: SMS + email + DingTalk Robot
    -   Info: Mail + DingTalk Robot
-   Message Note: Customize alarm message replenishment information. When you fill in your email remarks, your comments are included in the Message notification that is being sent to the alarm.


## Managing alarm rules {#section_zyz_szm_vdb .section}

Cloud monitoring provides users with three portal management alarm rules, respectively, it applies the grouping page, the monitoring list page of various types of monitoring and the alarm rule list page of the alarm service..

-   Manage alarm rules in apply groups.

-   Manage alarm rules in host monitoring.

-   Manage alarm rules in each cloud service monitor.

-   Use alarm rules in site monitoring.

-   Managing alarm rules in custom monitoring


