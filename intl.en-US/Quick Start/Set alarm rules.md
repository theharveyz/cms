# Set alarm rules {#concept_vrj_2mb_5db .concept}

## Scenarios {#section_jt2_kmb_5db .section}

CloudMonitor offers alarm rule service to notify through alarms on the metric data, if any exception occurs.  You can set alarm rules to specify how the alarm system checks the metric data and sends notifications when alarms are triggered.

If you set alarm rules for important metrics you are notified immediately if any metric data exceptions occurs. This helps to troubleshoot the issue in time.

**Note:** 

-   Alarm rules have silent period. When exceptions occur, alarms are sent only once in 24 hours to avoid alarm storms.
-   By default, CloudMonitor adds the contact name that you specify while account registration as the alarm contact. Moreover, it creates alarm contact group for that person.

## Introduction {#section_hwz_bjg_vdb .section}

-   Supports setting alarm rules for any monitoring metrics of CloudMonitor.
-   Supports alarm settings for all resources, apply grouping, and single instance ranges rules.
-   Supports setting the alarm rule validity period and customizing the time period during which the alarm rule takes effect.
-   Supports setting up alarm notification methods for different channels, customizing mail themes, message notes.

## Procedure {#section_jky_tmb_5db .section}

1.   Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/cloud/ecs).
2.  Add contacts and contact groups, see alarm contacts and alarm contact groups.
3.  Create an alarm rule. All monitoring features of cloud monitoring support the setting of alarm rules. Please check each module's use documentation for specific use steps.

