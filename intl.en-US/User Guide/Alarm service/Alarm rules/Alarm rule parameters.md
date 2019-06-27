# Alarm rule parameters {#concept_270434 .concept}

This topic describes parameters of a threshold alarm rule.

## Parameters {#section_qw0_so5_x63 .section}

-    Product: the name of the monitored service, such as ECS, RDS, or OSS.
-    Resource Range: the scope of the alarm rule. Valid values: All Resources, Application Groups, and Instances. If you set Resource Range to All Resources, the alarm rule is applicable to 1,000 instances or fewer. If the number of monitored resources is more than 1,000, you may not receive alarms when the specified metric reaches the threshold. We recommend that you add resources to service-specific application groups before creating the alarm rule.
    -    All Resources: specifies that the alarm rule is applicable to all your instances of the specified service. For example, you set Resource Range to All Resources and set the alarm threshold for ApsaraDB for MongoDB CPU usage to 80%. CloudMonitor generates an alarm when the CPU usage of any of your ApsaraDB for MongoDB instances is higher than 80%.
    -    Application Groups: specifies that the alarm rule is applicable to all instances in an application group. For example, you set Resource Range to Application Groups and set the alarm threshold for ECS instance CPU usage to 80%. CloudMonitor generates an alarm when the CPU usage of any of the ECS instances in your application group is higher than 80%.
    -    Instances: specifies that the alarm rule is applicable to a specified instance. For example, you set Resource Range to Instances and set the alarm threshold for ECS instance CPU usage to 80%. CloudMonitor generates an alarm when the CPU usage of the ECS instance is higher than 80%.
-    Alarm Rule: the name of the alarm rule.

-    Rule Description: the content of the alarm rule. This parameter defines the metric conditions that cause alarms. For example, the rule is described as follows: the average CPU usage in one minute is greater than or equal to 90%. CloudMonitor generates an alarm when the average CPU usage in one minute is greater than or equal to 90%.

     **Alert rule example**: in host monitoring, a data point on the metric of a single host is reported at a 15-second interval. Therefore, 20 data points are reported in 5 minutes.

    -   Average CPU usage in 5 minutes greater than 90% specifies that the average value of the 20 data points on CPU usage reported in 5 minutes is greater than 90%.
    -   CPU usage in 5 minutes always greater than 90% specifies that the values of all the 20 data points on CPU usage reported in 5 minutes are greater than 90%.
    -   CPU usage in 5 minutes greater than 90% for once specifies that the value of at least one of the 20 data points on CPU usage reported in 5 minutes is greater than 90%.
    -   Total Internet outbound traffic in 5 minutes greater than 50 Mbit/s specifies that the sum of the values of the 20 data points on Internet outbound traffic reported in 5 minutes is greater than 50 Mbit/s.
-    **Mute For**: CloudMonitor sends an alarm only after detecting the specified exceptions consecutively for specified times.
-    **Effective Period**: the period when an alarm rule is effective. The system only sends alarms within the effective period according to the alarm rule. The system only records alarms if the alarms occur during a non-effective period.
-    **Notification Contact**: the contact group that CloudMonitor sends alarms to.
-    **Alarm Levels**: specifies the alarm severity level that corresponds to a specified notification method. Valid values: CRITICAL, WARN, and INFO.
    -   INFO: sends alarms by means of emails and DingTalk ChatBot.
-    **Email Remarks**: custom supplementary information of an alarm email. CloudMonitor sends the remarks along with the alarm email.

