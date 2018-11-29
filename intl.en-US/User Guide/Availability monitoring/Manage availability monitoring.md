# Manage availability monitoring {#concept_i1w_jky_5db .concept}

Availability monitoring periodically detects whether a specified local or remote path or port responds properly, and sends an alarm notification if a response timeout or status code error occurs. This helps you quickly know when local or remote services are unresponsive.

**Note:** 

-   The availability monitoring function requires the CloudMonitor agent to work properly. When using this function, ensure that the CloudMonitor agent has been installed on the host.
-   Monitoring is performed once a minute.

## Create availability monitoring {#section_lyf_x4f_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left navigation pane, click **Application Groups**. The Application Groups page is displayed.
3.  Select the application group for which you want to create availability monitoring, and then click **Group Name**. The application group details page is displayed.
4.  In the left navigation pane, select **Availability Monitoring**. The availability monitoring management page is displayed.
5.  In the upper-right corner of the page, click **Create Configuration** to open the Create Availability Monitoring page.
6.  Selecting the target server, allows you to configure the same probe rules for all machines in the cluster, you can also configure the same detection rules for only some machines.
7.  Select the probe type and the probe target: supports URL/IP, RDS, OSS, redis.
    -   Selecting RDS, redis displays the relevant instances and access addresses in your grouping.
    -   When you select an HTTP protocol probe,, supports configuring Matching content for head, get, POST request methods, and return values.
8.  Select the alarm configuration, alarm support status code and response time, any configuration that reaches the threshold will trigger an alarm. The alarm is sent to the group of contacts to which the grouping is applied.
    -   Status Code alarm: the alarm is triggered when the status code of the probe satisfies the alarm settings.
    -   Notification method: the sending channel of the alarm notification.
    -   Advanced Configuration: supports both channel silence and effective time configurations. Channel silence time means that if the alarm does not return to normal after it has occurred, how often do I repeat an alarm notification. The effective time refers to the effective time of the alarm rule, checks whether the monitoring data requires an alarm only during the effective time.

## Viewing availability monitoring tasks {#section_ig1_xpf_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click application grouping in the left-hand navigation bar to go to the app grouping page.
3.  Select the app grouping for which you want to view availability monitoring, click the app grouping name to enter the app grouping details page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the Availability Monitoring page. The list shows the tasks that apply all availability monitoring in the grouping.

## View monitoring results {#section_xcr_zrf_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click application grouping in the left-hand navigation bar to go to the app grouping page.
3.  Select the app grouping for which you want to view availability monitoring, click the app grouping name to enter the app grouping details page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the Availability Monitoring page.
5.  You can view monitoring results in the list.
    -   When the task probe does not have an alarm, the number of exception machines in the list is 0.
    -   When an alarm occurs for a probe exception, the number of machines that have an alarm is displayed in the list, click exception numbers to view the exception machine details.
    -   Exception details.

## Modify availability monitoring tasks {#section_pzk_vsf_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click application grouping in the left-hand navigation bar to go to the app grouping page.
3.  Select the app grouping that needs to modify the availability monitoring, click the app grouping name to go to the app grouping details page.
4.  Select availability monitoring on the left-hand menu of the page to enter the administration page for availability monitoring.
5.  Select the task that needs to be modified, click Modify in the action to go to The modify page.
6.  Edit content on the modify page and save the configuration.

## View alarm logs {#section_tdx_dtf_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click application grouping in the left-hand navigation bar to go to the app grouping page.
3.  Select the app grouping that needs to view the alarm history, click the app grouping name to go to the app grouping details page.
4.  Select alarm history on the left-hand menu of the page, and go to the alarm history page to view the alarm history details.

## Enable or disable monitoring tasks {#section_l2d_gvf_vdb .section}

The local health check supports enabling or disabling the probe task, when disabled, the task no longer performs health checks and alarms, when enabled, the task re-starts the probe and fires the alarm when it meets the alarm rule settings.

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Click application grouping in the left-hand navigation bar to go to the app grouping page.
3.  Select the app grouping that needs to be enabled or disabled for availability monitoring, and click the app grouping name, enter the application grouping details page.
4.  Select availability monitoring on the left-hand menu of the page to enter the task management page for availability monitoring.
5.  Select the task that you want to enable or disable, and click enable or disable in the action to modify the task status.

