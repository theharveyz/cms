# Custom monitoring {#concept_w1n_r2w_tdb .concept}

## Overview {#section_xr1_v1b_5db .section}

Customized Monitoring allows you to customize monitoring metrics and alarm rules. With this feature, you can monitor desired business metrics and report collected monitoring data to CloudMonitor, so that CloudMonitor can process the data and trigger alarms for the monitored results.

What is the difference between event monitoring and customized monitoring?

Event monitoring is designed for reporting, query, and alarm scenarios of discontinuous event monitoring data. Custom monitoring is used when monitored data collected cyclically and continuously in the time series is reported and queried and alerts are generated.

## Procedure {#section_cns_gbb_5db .section}

1.  Report monitoring data.
2.  Search monitoring data
    1.  View all Customized Monitoring data
        1.  Log in to the CloudMonitor console.
        2.  Click custom monitoring in the left-hand navigation bar.
        3.  Select the corresponding application grouping and monitoring items to enter the time series details page.
        4.  Check the time series you want to view.
3.  Set an alert policy.
    1.  Click Apply grouping in the navigation bar, click the groups you want, and then click customize monitoring in the navigation bar.

        Or click customize monitoring in the navigation bar to select the corresponding application grouping and monitoring items, enter the time series details page.

    2.  3. Select the time sequence for which you need to create alarm rules. Click Set Alarm Rules in the Action column.
    3.  Go to the create alarm Rule Page, fill in the alarm rule name, select the appropriate monitoring item, dimension, alarm policy and notification method.

