# Glossary {#concept_um1_sv4_zdb .concept}

|Term|Description|
|:---|:----------|
|Site monitoring|Used to detect URL and IP availability, support the creation of HTTP, ICMP, TCP, UDP, DNS, POP3, SMTP, and FTP protocol detection points, and retrieve the status codes and response times of detected objects.|
|Cloud service monitoring|Provides performance metrics to monitor and manage data from several Alibaba Cloud products, such as ECS, RDS, Server Load Balancer, and OSS, among others.|
|Custom monitoring|Allows you to create custom metrics and use scripts to monitor, manage, and report data based on your business requirements.|
|Alarm service|Allows you to set alarm rules for the various metrics used in the monitoring services provided by CloudMonitor. Alarms are triggered when the monitoring data of a specific metric or metrics meets the condition or conditions specified in the alarm rules you set.|
|Metric|The data types you specify or are used by default as monitoring indicators. For example, response time and status code are the default metrics used for HTTP monitoring. Several metrics are used to monitor ECS instances, among which include CPU and memory usage.|
|Dimension|Used to locate metric data. For instance, the metric Disk I/O involves two dimensions: instance and disk name. Dimensions are also used to locate unique data. Currently, in custom monitoring, dimensions are represented by field information.|
|Alarm rule|A condition you make that is used to trigger an alarm when a certain threshold is met for metric data within a specific period. The following is an example alarm rule: an alarm is triggered when the memory usage of an instance is greater than or equal to 50% for three consecutive periods of 5 minutes, or 15 minutes.|
|Mute period|A condition you can set so that an alarm is muted and will no longer be triggered within the period you specify even when the condition specified in your alarm rule is met. A mute period can be set up to 24 hours.|
|Alarm contact|The recipient of an alarm message.|
|Alarm contact group|Sometimes abbreviated as contact group. A group of alarm contacts, which contains one or more alarm contacts. When configuring an alarm rule, you can specify the group of alarm contacts that will receive alarm notifications. The alarm system automatically sends alarm notifications to alarm group contacts based on the settings in the alarm rule when an alarm is triggered.|
|Notification method|The method by which an alarm notification is sent to an alarm contact or alarm contact group, which includes SMS message and email.|

