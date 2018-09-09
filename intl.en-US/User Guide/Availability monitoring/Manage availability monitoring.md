# Manage availability monitoring {#concept_i1w_jky_5db .concept}

Availability monitoring periodically detects the responsiveness of specified local paths or ports and sends an alarm notification when the response lapses or an error status code is returned. This helps you to immediately detect when the local or remote services are unresponsive.

**Note:** 

-   The availability monitoring function requires the CloudMonitor agent to work appropriately. You should ensure that the CloudMonitor agent is preinstalled on the relevant machines.
-   Monitoring is performed every minute.

## View availability monitoring tasks {#section_ig1_xpf_vdb .section}

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  Select **Application Groups** from the left-side navigation pane to go to the **Application Groups** page.
3.  Select the application group for which you want to create an availability monitoring task, and click the **Group name** to go to the **Application Groups** page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the **Availability Monitoring** page.
5.  Click**Create Configuration** in the upper-right corner of the page to go to the **Create Local Health Check**page.
6.  Select a test source. You can configure the same testing rules for some or all machines in the group.
7.  Select the test type and test target. This function supports URL/IP address, RDS, OSS, and Redis. If you select RDS or Redis, the interface will show the relevant instances and addresses in the group.

    **Note:** 

    -   If you select HTTP for the test, it will allow you to configure matching rules for HEAD, GET, and POST request methods and returned values.
8.  Select an **Alarm Configuration**. Alarms can be configured by status code or response time. An alarm is triggered when the returned status code is the same as the setting or no response is returned after the predefined timeout threshold has lapsed. The alarm will be sent to the contact group associated with the application group.

    **Note:** 

    -   Status code alarm: An alarm is triggered when the returned status code is the same as the setting.

    -   Notification method: It is the method by which alarm notifications are sent.

    -   Advanced configuration: Either channel silence time or effective time can be used. The channel silence time is the period after which an alarm is sent again. And also, if the exception persists even after the alarm is triggered. The effective time is the time when an alarm rule becomes effective. The availability monitoring function checks the metric data and determines whether to trigger an alarm at the time when the alarm rule is effective.


## **View availability monitoring tasks** {#section_sjj_4mx_y2b .section}

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  Select **Application Groups** from the left-side navigation pane to go to the **Application Groups** page.
3.  Select the application group for which you want to create an availability monitoring task, and click the **Group name** to go to the **Application Groups** page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the **Availability Monitoring** page.
5.  The list will display all the monitoring tasks available for that application group.

## View monitoring results {#section_xcr_zrf_vdb .section}

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  Select **Application Groups** from the left-side navigation pane to go to the **Application Groups** page.
3.  Select the application group for which you want to create an availability monitoring task, and click the **Group name** to go to the **Application Groups** page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the **Availability Monitoring** page.

    **Note:** The list will display the following monitoring results:

    -   When no alarm is triggered, the list shows that the number of machines that have triggered alarm is zero.

    -   When an alarm is triggered, the list shows the number of machines that have triggered alarm. Click the number to view the machine details.


## Modify availability monitoring tasks {#section_pzk_vsf_vdb .section}

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  Select **Application Groups** from the left-side navigation pane to go to the **Application Groups** page.
3.  Select the application group for which you want to create an availability monitoring task, and click the **Group name** to go to the **Application Groups** page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the **Availability Monitoring** page.
5.  Select the task you want to modify and click **Modify** from the **Actions** column to go to the edit page.
6.  Enter all the relevant details and click **Save** to confirm the changes.

## View alarm history {#section_tdx_dtf_vdb .section}

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  Select **Application Groups** from the left-side navigation pane to go to the **Application Groups** page.
3.  Select the application group for which you want to create an availability monitoring task, and click the **Group name** to go to the **Application Groups** page.
4.  Select **Alarm History** from the left-side navigation pane to go to the **Alarm History** page and here you can view the alarm history.

## Enable or disable a monitoring task {#section_l2d_gvf_vdb .section}

You can enable or disable availability monitoring tasks. A disabled task does not monitor or trigger alarms. The availability monitoring task can only restart monitoring and triggering alarms as per the set alarm rules, when the tasks are reinstated.

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  Select **Application Groups** from the left-side navigation pane to go to the **Application Groups** page.
3.  Select the application group for which you want to create an availability monitoring task, and click the **Group name** to go to the **Application Groups** page.
4.  Select **Availability Monitoring** from the left-side navigation pane to go to the **Availability Monitoring** page.
5.  Select the task you want to enable or disable and click **Enable** or **Disable** from the **Actions** column to modify the task status as per the requirement.

