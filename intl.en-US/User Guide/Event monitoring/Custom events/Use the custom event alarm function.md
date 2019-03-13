# Use the custom event alarm function {#concept_gwp_sps_zgb .concept}

This topic describes how to use the custom event alarm function.

## Overview {#section_sfc_gkd_v2b .section}

To notify you of data exceptions, the custom event alarm function provides the following two notification methods:

-   Notifications sent as e-mails or DingTalk messages
-   Notifications sent to your alarm callback URL for scenario-oriented troubleshooting

## Procedure {#section_jry_jkd_v2b .section}

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  Choose **Event Monitoring** \> **Alarm Rules**.
3.  Click **Create Event Alerts**.

    The following figure shows the displayed Create / Modify Event Alerts dialog box.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135623/155244183640129_en-US.png)

4.  In the **Basic Information** area, enter a name for the alarm rule.
5.  In the **Event alert** area, configure the following settings:
    1.  Set **Event Type** to **Custom Event**.
    2.  Set **Application Groups** to the target application group.
    3.  Enter a **Event Name**.
    4.  Select an option from the **Rule Description** drop-down list and set the accumulation times.
    5.  Choose your preferred **Notification Method**.
    6.  In the **Advanced Configuration** area, set **Effective From** and **Alarm Callback**.
        -   **Effective From**: Indicates the time from which the alarm rule begins to take effect. The alarm rule checks whether to report alarms for monitoring data exceptions only during the period of time that you specified.
        -   **Alarm Callback**: Enter a URL that can be accessed from the Internet. CloudMonitor will then send alarm notifications to the URL using an HTTP POST request.
    7.  Click **OK**.

When the reported custom event meets the conditions specified by the alarm rule, a notification is sent.

