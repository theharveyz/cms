# Custom monitoring {#concept_w1n_r2w_tdb .concept}

## Overview {#section_xr1_v1b_5db .section}

Customized Monitoring allows you to customize monitoring metrics and alarm rules.  With this feature, you can monitor intended business metrics and report collected monitoring data to CloudMonitor, so that CloudMonitor can process the data and trigger alarms for the monitored results.

What is the difference between event monitoring and customized monitoring?

Event monitoring is designed for reporting, query, and alarm scenarios of discontinuous event monitoring data.  Customized monitoring is designed for reporting, query, and alarm scenarios of time sequence monitoring data which is collected periodically and continuously.

## Procedure {#section_cns_gbb_5db .section}

1.  [Report monitoring data](../../../../intl.en-US/User Guide/Custom monitoring/Reporting Monitoring Data.md#)
2.  Search monitoring data
    1.  View all Customized Monitoring data
        1.  Log on to the[CloudMonitor console](https://cloudmonitor.console.aliyun.com).
        2.  Click **Customized Monitoring**in the navigation pane.
        3.  Select the corresponding application group and monitoring metrics to go to the Time Sequence details page.
        4.  Select the time sequence to view.

            ![](images/1059_en-US.png)

3.  Set alarm rules
    1.  Click Apply grouping in the navigation bar, click the groups you want, and then click customize monitoring in the navigation bar.

        Select the corresponding application group and monitoring metrics to go to the Time Sequence details page.

    2.  Select the time sequence for which you need to create alarms. Click Set **Alarm Rules** in the **Action**column.
    3.  Go to the Create Alarm Rules page, and enter the name of the alarm rule, then set the corresponding alarm policy and notification method.

