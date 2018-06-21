# Managing availability monitoring {#concept_i1w_jky_5db .concept}

Availability monitoring periodically detects whether a path or port is responding properly, locally or remotely, to you, send an alarm notification when a response timeout or status code error occurs. Help you quickly discover unresponsive local or dependent remote services.

**Note:** 

-   Use the availability monitoring feature to rely on the cloud monitoring plug-in, using this feature requires ensuring that the cloud monitoring plug-in is installed on the machine.
-   The monitoring frequency is 1 per minute.

## Create availability monitoring {#section_lyf_x4f_vdb .section}

 \[/concept/conbody/section/p/ul \{"- topic/ol"\}\) 3.  Log in to the cloud monitoring console, select Application grouping on the left-hand menu of the page, and enter the application grouping page.
 5.  Select the app grouping that needs to be created for availability monitoring, click the app grouping name to go to the app grouping details page.
 7.  Select availability monitoring on the left-hand menu of the page to enter the availability Monitoring Management page.
 9.  Click the new configuration button in the upper-right corner of the page to enter the Edit page.
 11. Selecting the probe source allows you to configure the same probe rules for all machines in the cluster, you can also configure the same detection rules for only some machines.
 13. Select the probe type and the probe target: supports URL/IP, RDS, OSS, redis. Selecting RDS, redis displays the relevant instances and access addresses in your grouping.
    -   When you select an HTTP protocol probe,, supports configuring Matching content for head, get, POST request methods, and return values.

 15. Select the alarm configuration, alarm support status code and response time, any configuration that reaches the threshold will trigger an alarm. The alarm is sent to the group of contacts to which the grouping is applied.
    -   Status Code alarm: the alarm is triggered when the status code of the probe satisfies the alarm settings.
    -   Notification method: the sending channel of the alarm notification.
    -   Advanced Configuration: supports both channel silence and effective time configurations. Channel silence time means that if the alarm does not return to normal after it has occurred, how often do I repeat an alarm notification. The effective time refers to the effective time of the alarm rule, checks whether the monitoring data requires an alarm only during the effective time.

 \(ul\] 

## Viewing availability monitoring tasks {#section_ig1_xpf_vdb .section}

1.  Log in to the cloud monitoring console, select Application grouping on the left-hand menu of the page, and enter the application grouping page.
2.  Select the app grouping for which you want to view availability monitoring, click the app grouping name to enter the app grouping details page.
3.  Select the availability monitor on the left-hand menu of the page to enter the availability monitor page.
4.  The list shows the tasks that apply all availability monitoring in the grouping.

## View monitoring results {#section_xcr_zrf_vdb .section}

1.  Log in to the cloud monitoring console, select Application grouping on the left-hand menu of the page, and enter the application grouping page.
2.  Select the app grouping for which you want to view availability monitoring, click the app grouping name to enter the app grouping details page.
3.  Select the availability monitor on the left-hand menu of the page to enter the availability monitor page.
4.  You can view monitoring results in the list.
    -   When the task probe does not have an alarm, the number of exception machines in the list is 0.

        ![](images/1897_en-US.png)

    -   When an alarm occurs for a probe exception, the number of machines that have an alarm is displayed in the list, click exception numbers to view the exception machine details.

        ![](images/1899_en-US.png)

    -   Exception details.

        ![](images/1901_en-US.png)


## Modify availability monitoring tasks {#section_pzk_vsf_vdb .section}

1.  Log in to the cloud monitoring console, select Application grouping on the left-hand menu of the page, and enter the application grouping page.
2.  Select the app grouping that needs to modify the availability monitoring, click the app grouping name to go to the app grouping details page.
3.  Select availability monitoring on the left-hand menu of the page to enter the administration page for availability monitoring.
4.  Select the task that needs to be modified, click Modify in the action to go to The modify page.
5.  Edit content on the modify page and save the configuration.

## View alarm history {#section_tdx_dtf_vdb .section}

1.  Log in to the cloud monitoring console, select Application grouping on the left-hand menu of the page, and enter the application grouping page.
2.  Select the app grouping that needs to view the alarm history, click the app grouping name to go to the app grouping details page.
3.  Select alarm history on the left-hand menu of the page, and go to the alarm history page to view the alarm history details.

## Enable or disable monitoring tasks {#section_l2d_gvf_vdb .section}

The local health check supports enabling or disabling the probe task, when disabled, the task no longer performs health checks and alarms, when enabled, the task re-starts the probe and fires the alarm when it meets the alarm rule settings.

1.  Log in to the cloud monitoring console, select Application grouping on the left-hand menu of the page, and enter the application grouping page.
2.  Select the app grouping that needs to be enabled or disabled for availability monitoring, and click the app grouping name, enter the application grouping details page.
3.  Select availability monitoring on the left-hand menu of the page to enter the task management page for availability monitoring.
4.  Select the task that you want to enable or disable, and click enable or disable in the action to modify the task status.

