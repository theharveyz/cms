# Manage availability monitoring {#concept_i1w_jky_5db .concept}

Availability monitoring conducts periodical detection tasks to check whether specified local or remote paths or ports respond properly and sends alarm notifications if response timeouts occur or status codes indicate errors based on the conditions specified in your alarm rules. This function can help you to quickly learn if local or remote services are unresponsive or abnormal, improving overall O&M and management efficiency.

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

