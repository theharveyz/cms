# Alarm service {#concept_vrj_2mb_5db .concept}

## Application scenarios {#section_jt2_kmb_5db .section}

The CloudMonitor alarm service can generate alarms during data monitoring. You can set alarm rules to specify how the alarm system checks the data and sends alarm notifications when alarms are triggered.

By setting alarm rules for important metrics, you can monitor for, and immediately handle, any system exceptions.

**Note:** 

-   Alarm rules have specific behaviors. For example, if an exception occurs, only one alarm notification will be sent in the first 24 hours to avoid sending unnecessary alarms.
-   By default, CloudMonitor adds the contact name specified during account registration as the alarm contact, and also creates an alarm contact group for the alarm contact.

## Features {#section_hwz_bjg_vdb .section}

With the CloudMonitor alarm service, you can:

-   Set alarm rules for any metrics of CloudMonitor.
-   Set alarm rules for all resources, application groups, and instances.
-   Set the alarm rule validity period and customize the time period during which the alarm rule takes effect.
-   Set the notification methods for different channels, and customize the mail themes and email remarks.

## Procedure {#section_jky_tmb_5db .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Add a contact or contacts and a contact group. For details, see [Manage alarm contacts and alarm contact groups](../../../../reseller.en-US/User Guide/Alarm Service/Manage alarm contacts and alarm contact groups.md#).
3.  Create an alarm rule as required. For details, see [Manage alarm rules](../../../../reseller.en-US/User Guide/Alarm Service/Manage alarm rules.md#).

