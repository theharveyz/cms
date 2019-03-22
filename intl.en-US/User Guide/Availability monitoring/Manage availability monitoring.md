# Manage availability monitoring {#concept_i1w_jky_5db .concept}

Availability monitoring conducts periodical detection tasks to check whether specified local or remote paths or ports respond properly and sends alarm notifications if response timeouts occur or status codes indicate errors based on the conditions specified in your alarm rules. This function can help you to quickly learn if local or remote services are unresponsive or abnormal, improving overall O&M and management efficiency.

**Note:** 

-   The CloudMonitor agent must be installed before you can use the availability monitoring function. Check that you have installed the CloudMonitor agent on your specified instances before using this function.
-   Once working, monitoring tasks are performed once a minute.

## Create availability monitoring tasks {#section_lyf_x4f_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Application Groups**.
3.  Find the target application group and click the group name.
4.  In the left-side navigation pane, select **Availability Monitoring**.
5.  In the upper-right corner of the page, click **Create Configuration** to open the Create Availability Monitoring page.
6.  Enter the task name and select the target server. You can select all servers in the application group to configure the same availability monitoring rules for them, or select some severs in the application group.
7.  Select the detection type and the detection target: **URL or IP address**, **ApsaraDB for RDS**, and **ApsaraDB for Redis** are supported.
    -   If you selecting **ApsaraDB for RDS** or **ApsaraDB for Redis**, relevant instances in the application group and access addresses are displayed.
    -   If you select **HTTP\(S\)** for the **Detection Target**, you can configure matching content for HEAD, GET, and POST requests and return values.
8.  Set the alarm rules. Status code and response time rules are supported for alarms. Any configuration that meets a condition specified in an alarm rule will trigger an alarm. An triggered alarm is sent as a notification to the alarm contact group that is associated to the application group.
    -   Status code alarm: An alarm that is triggered when the probe status code meets the specified alarm rules.
    -   Notification method: The means by which alarm notifications are sent, such as email or SMS message.
    -   Advanced configuration: Both effective and mute period configurations are supported. Effective period refers to a period in which an alarm rule is effective with alarms possibly triggered in the case that the conditions specified in your alarm rules are met. Mute period refers to a period in which your alarm rules are muted so that alarm notifications will be silenced even if conditions specified in your alarm rules are met.

## Viewing availability monitoring tasks {#section_ig1_xpf_vdb .section}

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click Application Groups in the left-hand navigation bar to go to the application groups page.
3.  Select the application groups for which you want to view availability monitoring, then click the application group name to enter the application group details page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the Availability Monitoring page. A list displaying the tasks that apply all availability monitoring in the group is displayed.

## View monitoring results {#section_xcr_zrf_vdb .section}

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click **Application Groups** in the left-hand navigation bar to go to the Application Groups page.
3.  Select the **Application Groups** for which you want to view availability monitoring, then click the application group name to enter the application groups details page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the Availability Monitoring page.
5.  You can view monitoring results in the list.
    -   When the task probe does not trigger an alarm, the number of faulty instances in the list is 0.
    -   When an alarm is triggered for a probe exception, the number of instances that triggered an alarm is displayed in the list, click exception numbers to view the faulty instance details.
    -   Exception details.

## Modify availability monitoring tasks {#section_pzk_vsf_vdb .section}

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click **Application Groups** in the left-hand navigation bar to go to the Application Groups page.
3.  Select the **Application Groups** that needs to modify the availability monitoring, click the application group name to go to the app grouping details page.
4.  Select availability monitoring on the left-hand menu of the page to enter the management page for availability monitoring.
5.  Select the task that needs to be modified, click Modify in the action to go to the modify application groups page.
6.  Edit content on the modify application groups page and save the configuration.

## View alarm logs {#section_tdx_dtf_vdb .section}

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click **Application Groups** in the left-hand navigation bar to go to the Application Groups page.
3.  Select the application groups that needs to view the alarm logs, click the application group name to go to the application group details page.
4.  Select **Alarm Logs** on the left-hand menu of the page, and go to the alarm logs page to view the alarm log details.

## Enable or disable monitoring tasks {#section_l2d_gvf_vdb .section}

Enabling or disabling monitoring tasks is supported for local health checks. When a task is disabled, health checks are no longer performed and alarms are no longer triggered for the task. However, when a task is enabled, probing is re-started and alarms will be triggered when the conditions specified in alarm rule settings are met.

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click **Application Groups** in the left-hand navigation bar to go to the Application Groups page.
3.  Select the application groups that needs to be enabled or disabled for availability monitoring, and click the application group name, enter the application group details page.
4.  Select availability monitoring on the left-hand menu of the page to enter the task management page for availability monitoring.
5.  Select the task that you want to enable or disable, and click enable or disable in the action to modify the task status.

