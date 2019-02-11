# Create application groups {#concept_j5l_dwf_vdb .concept}

This topic describes how to group your cloud resources by creating application groups so that you can manage your resources and alarm rules on a grouped basis.

## Scenarios {#section_h5g_3fv_vdb .section}

If you have purchased multiple products on Alibaba Cloud, you can group them together in a centralized manner by creating application groups. With application groups, you can manage resources of different regions and products, such as servers, databases, object storage, and cache, based on your business modules. In addition, you can easily manage alarm rules and view the monitoring data of these grouped resources.

## Application group modes {#section_nw2_ztr_pgb .section}

Instances can be added to application groups using dynamic or static mode.

-   Dynamic mode: When creating an application group, you can set name rules for instances so that instances which meet your name rules will be automatically added into the application group. If you want to add or remove instances to or from the group in the future, you only need to modify the instance names to complete these configurations. Currently, dynamic mode is supported only by ECS, ApsaraDB for RDS, and SLB instances.
-   Static mode: With static mode, you need to manually add instances to an application group.

## Create an application group {#section_wjc_kfv_vdb .section}

**Note:** 

-   Up to 1,000 resource instances can be added to each application group.
-   Up to 100 application groups can be created under each account.

Procedure

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Application Groups**.
3.  In the upper-right corner of the displayed page, click **Create Group**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6144/15498787236597_en-US.png)
4.  Enter **Basic Information**: Enter the group name and select one or more contact groups to receive alarm notifications.
5.  Set **MonitorAlarm**: Select one or more templates to initialize alarm rules for the instances in the group \(optional\), and select the notification method. If you turn on the **Initialize Agent Installation** switch, the CloudMonitor agent will be installed on all servers in the group to collect monitoring data.
6.  Set **Event Monitor**: If you select the **Subscribe Event notification** check box, alarm notifications will be sent when critical-level and warning-level events occur in related resources in the group.
7.  Set **Add Instance dynamically**.
    -   You can set name rules to automatically add ECS instances that match the name rules to the group. Specifically, instances, including future instances, whose names contain, start with, or end with the words you specify will be automatically added to the group. A maximum of three rules can be added, and the relationship among the rules can be AND or OR.
    -   To add rules for ApsaraDB for RDS or SLB instances, click **Add Product**.
    -   To add instances of other Alibaba Cloud products, you need to add them manually after creating the application group.
8.  Click **Create Application Group**.

