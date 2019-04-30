# Create an alert rule for pods in Container Service for Kubernetes {#concept_hr3_hhx_bgb .concept}

This topic describes how to create an alert rule for one or more pods in Container Service for Kubernetes.

## Background information {#section_mbj_wf2_qgb .section}

CloudMonitor provides an additional alert function for Container Service for Kubernetes. This function monitors metrics such as CPU utilization and inbound bandwidth of Container Service, providing you with information about the usage of Container Service. After you deploy Container Service, CloudMonitor automatically involves Container Service into its monitoring system. You can log on to the CloudMonitor console and access the Container Services for Kubernetes page to view detailed monitoring data. After you configure an alert rule for a metric, you can receive alert notification when the metric data exceeds the defined threshold.

## Prerequisites {#section_grl_pj2_qgb .section}

We recommend that you perform the following operations before you create an alert rule for Container Service for Kubernetes: 1. Deploy Container Service. 2. Create application groups, alert contacts, and alert contact groups in the CloudMonitor console.

## Procedure {#section_ehp_vqx_bgb .section}

 **Precautions** 

-   Monitoring data is stored for up to 31 days.
-   You can view the monitoring data for up to 14 consecutive days.

 **Create an alert template for Container Service for Kubernetes** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Templates**. The **Alarm Templates** page is displayed.
3.  Click **Create Alarm Templates** in the upper-right corner. The Create Alarm Template page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/155661440034067_en-US.png)

4.  Configure template information: Set the service name to **Kubernetes** and configure related metrics.
5.  Click **Add**.

 **Apply the template to a Kubernetes application group** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Templates**. The **Alarm Templates** page is displayed.
3.  Click **Apply to Group** in the Actions column corresponding to the just-created alert template for Container Service for Kubernetes.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/155661440034071_en-US.png)

4.  Select the group for which you want to create an alert rule, and click **OK**.

## Subsequent operations {#section_ezq_fyy_bgb .section}

Alert notification for the Kubernetes application group is automatically sent to Default Contact Group. If you want all alerts for the Kubernetes application group to be sent to the same contact group, directly change the contacts in Default Contact Group.

 **Directly modify a contact group** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left navigation pane, choose **Alarms** \> **Alarm Contacts**. The **Alarm Contacts** page is displayed.
3.  Click the **Alarm Contact Group** tab. The Alarm Contact Group tab is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/155661440034072_en-US.png)

4.  Click the modification icon. On the Edit Group page that appears, change the contacts and click **OK**.

If you want alerts for different Kubernetes applications to be sent to different contact groups, you must modify the associated alert contact groups for each Kubernetes application group.

 **Modify the associated contact group of an application group** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Application Groups**. The **Application Groups** page is displayed.
3.  Find the Kubernetes application group and click the group name. The group details page is displayed.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/155661440034079_en-US.png)
4.  Click the modification icon. On the page that appears, change the contact group and click **OK**. All alerts for the Kubernetes application group will be sent to the new alert contact group.

You can use OpenAPI to modify the contact groups of multiple Kubernetes application groups.

 **Modify contact groups through OpenAPI** 

1.  Log on to [OpenAPI Explorer](https://api.aliyun.com).
2.  In the left-side cloud service list, click **CloudMonitor**. In the search box, enter UpdateMyGroups. Click the API in the search result. The API call page is displayed.
3.  Set GroupId to the group ID to be modified.
4.  Set ContactGroups to the contact group to which alert notification is to be sent.
5.  Click **Initiate a Call**.

