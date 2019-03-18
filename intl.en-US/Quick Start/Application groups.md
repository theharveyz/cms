# Application groups {#concept_mjr_s2w_tdb .concept}

## Application scenarios {#section_e5q_1kb_5db .section}

-   **Service-based resource management**

    Application groups allow enterprise-level users to categorize resources under their accounts and query monitoring and alarm information by service.

-   **Inspection and fault detection**

    Application groups provide features such as group health measurements, fault lists, and resource dashboards, which allow you to inspect resource usage and quickly locate any faulty resources and determine alarm causes.

-   **Improved resource usage efficiency**

    Application groups can aggregate and display multidimensional monitoring data, helping you query monitoring data from single instances or groups, so that you can quickly locate abnormally high resource usage.


## Features {#section_svf_ckb_5db .section}

With application groups, you can:

-   Manage your cloud resources across products and regions by service.
-   Manage all resources in a group by configuring only one alarm rule, helping to improve O&M efficiency.
-   Identify faulty instances immediately by checking the fault list.
-   Display the charts in a group as required on the application group details page.

## Procedure {#section_xtx_hkb_5db .section}

To create an application group, perform the following steps:

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, select **Application Groups**. The **Application Groups** page is displayed.
3.  In the upper-right corner of the page, click **Create Group**. The **Create Group** page is displayed.
4.  Enter the product group name and select a contact group.
5.  Select an alarm template.
6.  Add an instance dynamically. For example, you can add an ECS instance according to the dynamic rule you have created. All instances that are created according to the rule are automatically added to the application group.
7.  Add products. The ECS products are initialized by default. You can click **Add Product** and **Delete** to specify the product scope.
8.  Click **Create Application Group**.

