# Alarm service {#concept_vrj_2mb_5db .concept}

## Application scenarios {#section_jt2_kmb_5db .section}

The CloudMonitor alarm service generates alarms during data monitoring. You can set alarm rules to specify how the alarm system checks data and how it sends alarm notifications when alarms are triggered.

By setting alarm rules for important metrics, you can monitor for, and immediately handle, any system exceptions.

**Note:** 

-   Alarm rules have a default mute period of 24 hours, so that, if an exception occurs, only one alarm notification will be sent in the first 24 hours so to avoid sending unnecessary alarms.
-   By default, CloudMonitor adds the contact name specified during account registration as the alarm contact and creates an alarm contact group for this alarm contact.

## Features {#section_hwz_bjg_vdb .section}

With the CloudMonitor alarm service, you can:

-   Set alarm rules for any of the metrics of CloudMonitor.
-   Set alarm rules for instances, application groups, and all resources.
-   Set the alarm rule effective period customizing the period of time where an alarm rule takes effect.
-   Set the notification methods for different channels and customize the subject and remarks for an email notification.

## Procedure {#section_jky_tmb_5db .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Add one or more contacts and contact groups. For more information, see [Manage alarm contacts and alarm contact groups](../../../../reseller.en-US/User Guide/Alarm service/Manage alarm contacts and alarm contact groups.md#).
3.  Create one or more alarm rules as required. For more information, see [Manage alarm rules](../../../../reseller.en-US/User Guide/Alarm service/Manage alarm rules.md#).

