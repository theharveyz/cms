# Create application groups {#concept_j5l_dwf_vdb .concept}

## Scenarios {#section_h5g_3fv_vdb .section}

Alibaba Cloud depth users who have purchased a variety of cloud products, add resources such as the same business-related server, database, object store, cache, and so on by applying grouping capabilities into the same application grouping. Managing alarm rules in a Grouped dimension and viewing monitoring data can greatly reduce administrative complexity, improve operational efficiency.

**Note:** 

-   Add up to 1000 resource instances per grouping.
-   When you create a grouping, if the initialization alarm rule is checked, cloud monitoring is based on the type of resource in your group, check if the average of 5 minutes exceeds the threshold and is notified by mail and Wangwang, the notification object is the alarm contact group that was selected when the apply grouping was created.

## Operation Steps {#section_wjc_kfv_vdb .section}

1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Select Apply grouping on the left-hand menu of the page to enter the apply grouping page.
3.  Click Create group in the upper-right corner of the page to enter the Edit page.
4.  Fill in the grouping name.
5.  Select the product you want to add.
    -   Default initialization for ECs and RDS Product, you can select the range of products for this grouping by adding a product, removing this product button
    -   Select the instances that need to be grouped in the product's list of corresponding instances.
6.  Select the notification object that receives the Alert Notification.
7.  Select whether to initialize alarm rules for grouping.
8.  Click the confirm button to save the apply grouping settings.

