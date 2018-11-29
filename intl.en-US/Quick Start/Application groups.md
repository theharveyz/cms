# Application groups {#concept_mjr_s2w_tdb .concept}

## Application scenarios {#section_e5q_1kb_5db .section}

-   Service-based resource management

    Application groups allow enterprise users to categorize resources under their cloud accounts and query monitoring and alarm information by service.

-   Inspection and fault location

    Application groups provide multiple features, including group health measurements, a faulty resource list, and group resource monitoring dashboards. These features allow you to periodically inspect resource usage, quickly locate any faulty resources, and identify the causes after receiving an alarm.

-   Higher resource usage

    Application groups can aggregate and display multidimensional monitoring data. This means that you can query group-based and aggregated monitoring data, or data of a single instance, to immediately locate abnormally high resource usage.


## Features {#section_svf_ckb_5db .section}

With application groups, you can:

-   Manage your cloud resources across products and regions by service.
-   Manage all resources in a group by configuring only one alarm rule, improving O&M efficiency.
-   Identify faulty instances immediately by checking the faulty resource list.
-   Display the monitoring charts in a group as required on the application group details page.

## Procedure {#section_xtx_hkb_5db .section}

To create an application group, perform the following steps:

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, select **Application Groups**.
3.  In the upper-right corner of the page, click **Create Group**.
4.  Enter the product group name and select a contact group.
5.  Select an alarm template.
6.  Add an instance dynamically. For example, you can add an ECS instance according to the dynamic rule you have created. All instances that are created according to the rule are automatically added to the application group.
7.  Click **Add Product** to add the required number of products. ECS products are initialized by default. You can also click **Delete** to remove products you no longer need.
8.  Click **Create Application Group**.

