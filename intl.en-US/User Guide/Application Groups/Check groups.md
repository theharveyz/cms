# Check groups {#concept_ucw_wgv_vdb .concept}

The group details page includes the fault list, alarm history, alarm rules, group resources, events, and group resource metric data.

## Group list {#section_xdm_t5b_wdb .section}

The group list displays all the groups on the CloudMonitor. You can also view the resources and health condition of each group.

**Parameters**

-   Group name: The name of a group.
-   Health condition: The alarm status of any group resource. The group is healthy when add, modify, and no active alarms for any group resource.  The group is said to be unhealthy  when any of the resources has active alarms.
-   VM count: VM count is the total number of servers \(ECS servers and other servers\) in the group.
-   Resource count: The total number of resource types in the group. For example, if the group has ECS, ApsaraDB for RDS, and Server Load Balancer instances, then the total number of resource count is three.
-   Unhealthy Count: The total number of instances with active alarms in the group.  For example, if two ECS instances and one ApsaraDB for RDS instance have active alarms, the number of unhealthy instances is three.
-   Creation time: The time when the group is created.
-   Actions: Four types of operations are supported namely copy this group and create a new group, enable all the alarm rules and disable all the alarm rules, and delete groups.

## Fault list {#section_zdp_cvb_wdb .section}

The fault list shows the resources with active alarms in your group.  This allows you to quickly view all the unhealthy instances and troubleshoot faults in time.

**Note:** 

-   When multiple metrics of a resource have active alarms all at the same time, the fault list displays the resource multiple times.  Each row of the list shows one metric with an active alarm.
-   Once you disable the rule hit by active alarms, the resources and metrics associated with the rule disappears from the fault list.

**Parameters**

-   Faulty resource: A resource with an active alarm.
-   Start time: Time when the first alarm is generated.
-   Status: Displays a message indicating that a resource has an active alarm.
-   Duration: The time duration when a faulty resource is in the alarm state.
-   Alarm rule name: The name of the alarm rule applied to a faulty resource.
-   Actions: Click Expand to view the metric trends of a faulty resource with an active alarm for past six hours, and compare the metric data with the alarm threshold value.

## Alarm history {#section_ynb_nbc_wdb .section}

Alarm history provides the account of all the alarm rules applied to a group.

**Note:** You can request for the alarm data history of the past three days. If the interval between the query start-time and end-time exceeds three days, the system prompts you to re-select the time range.

**Parameters**

-   Faulty resource: Resource with an active alarm.
-   Duration: The time during which a faulty resource is in the alarm state.
-   Occurrence time: The time when the alarm is generated.
-   Alarm rule name: The name of the alarm rule applied to a faulty resource.
-   Notification method: Method by which alarm notifications are sent.  These notifications are sent through SMS, email, or TradeManager.
-   Product type: The product type where the faulty resource belongs to.
-   Status: The status of the alarm rule such as the alarm state, cleared state, and channel silence state.
-   Notification object: A group of contacts who receive alarm notifications.

## Alarm rules {#section_pcd_kcc_wdb .section}

Alarm rules display the list of all the alarm rules applied to a group. You can select the preferred alarm rule from the list and can enable, disable, and/or modify the rules as per the requirement.

**Note:** The alarm rules list only displays the alarm rules applied to a specific group.  It does not show the alarm rules with Resource Range set to the All Resources or an Instance.

**Parameters**

-   Policy name: Name of an alarm rule \(policy\) specified when the policy is created.

-   Status: Displays whether or not, the resources associated with the alarm rules have active alarms.

    -   Normal state: All resources associated with the alarm rules are normal.
    -   Alarm state: At least one instance associated with the alarm rule has an active alarm.
    -   Insufficient data: At least one instance associated with the alarm rule has insufficient data and no instance has an active alarm.
-   Enable: Enables the alarm rule.

-   Product name: Name of the product which group resources belongs to.
-   Policy description: A brief description of alarm rules setting.
-   Actions: The optional operations include Modify, Enable, Disable, Delete, and Alarm History.

    -   Modify: You can click Modify to make changes in the alarm rule.
    -   Disable: Click Disable to disable the alarm rule. Once the alarm rule is disabled, the alarm service does not check whether metric data exceeds the threshold value.
    -   Enable: Click Enable to enable the alarm rule. Once you enable a previously disabled alarm rule, the alarm service checks the metric data and determines whether to trigger an alarm based on the alarm rule.
    -   Delete: Click Delete to delete the alarm rule.
    -   Alarm History: Click to view the alarm history of the alarm rule.

## Group resources {#section_spk_5bx_wdb .section}

Display all the resources of a group and health condition of the resource.

**Parameters**

-   Instance name: Instance name or ID of a resource.
-   Health condition: The alarm status of any group resource. The resource is healthy if no alarm is generated according to the corresponding alarm policy.  The resource is unhealthy if it has an active alarm.

## Event {#section_wc4_4cx_wdb .section}

Currently, the alarm rule \(policy\) provides the alarm history and records alarm policy operation events \(add, modify, and delete\), allowing you to trace any operation performed on a specific alarm rule.

**Note:** You can query event information over last 90 days.

**Parameters**

-   Occurrence time: The time when any event occurs.
-   Event name: The event names such as alarm generated, alarm cleared, create alarm rule, modify alarm rule, or delete alarm rule.
-   Event type: Events are classified into system events and alarm events.  System events include create alarm rule, delete alarm rule, and modify alarm rule. Alarm events include alarm generated and alarm cleared.
-   Event details: Provide details of an event.

## Metric chart {#section_uq2_5cx_wdb .section}

The lower section of the group details page displays the monitoring details of group resources.  By default, CloudMonitor initializes frequently used metric data. If you want to display more metric data or change the chart type, modify the charts and customize metric data and/or the chart type.

**Note:**  To obtain the OS metrics of ECS, you must install the CloudMonitor agent.

**Initialized metric data**

The following group data is initialized by default. If you want to view more metric data, click Add Metric Chart to add more metrics to the data.

|Product category|Metric|Chart type|Description|
|:---------------|:-----|:---------|:----------|
|ECS|CPU usage and Internet outbound bandwidth|Line chart|Displays the aggregate data of all servers in the group.|
|ApsaraDB for RDS |CPU usage, disk usage, IOPS usage, connection usage|Line chart|Displays the data of a single database instance.|
|Server Load Balancer|Outbound bandwidth and inbound bandwidth|Line chart|Displays the data of a single Server Load Balancer instance.|
|OSS|Storage size and GET/PUT request count|Line chart|Displays the data of a single bucket.|
|CDN|Downstream bandwidth and hit rate|Line chart|Displays the data of a single domain name.|
|EIP| Internet outbound bandwidth|Line chart|Displays the data of a single instance.|
|ApsaraDB for Redis|Memory usage, connection usage, and QPS usage|Line chart|Displays the data of a single instance.|
|ApsaraDB for MongoDB|CPU usage, memory usage, IOPS usage, and connection usage|Line chart|Displays the data of a single instance.|

