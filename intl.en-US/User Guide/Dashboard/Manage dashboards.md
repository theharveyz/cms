# Manage dashboards {#concept_x5q_k5y_5db .concept}

You can easily view, create, and delete dashboards. The procedure for these actions is as follows.

## View a dashboard {#section_ehx_55y_5db .section}

You can view a dashboard to view and monitor metrics from several different products and instances all within one area.

**Note:** 

-   CloudMonitor automatically initializes an ECS dashboard and displays ECS metrics.
-   CloudMonitor refreshes data measured in one-hour, three-hour, and six-hour periods automatically. However, data measured for more than six hours cannot be refreshed automatically.

Procedure

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Dashboard** \> **Custom Dashboard**.
3.  By default, **ECS-global-dashboard** is displayed. You can select another dashboard from the drop-down list.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6139/15451055161553_en-US.png)

4.  To view the dashboard in full screen, click **Full Screen** in the upper-right corner of the page.
5.  Select a time range. Click the time range button at the top of the page. From there, you can quickly select the time range shown in the charts of the dashboard. The time range you select apply to all the charts on the dashboard.
6.  Automatic refresh. After you turn on the **Auto Refresh** switch, whenever you select a query time span of 1 hour, 3 hours, or 6 hours, automatic refresh is performed every minute.
7.  The units of the metrics measured are displayed in parentheses for the chart name.
8.  When you rest the pointer over some point on a chart, values at that time point are displayed across all charts.

## Create a dashboard {#section_w1s_dxy_5db .section}

You can create a dashboard and customize the charts for when your business operations grow complex and the default ECS dashboard does not meet your monitoring requirements.

**Note:** Up to 20 charts can be created on one dashboard.

Procedure

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Dashboard** \> **Custom Dashboard**.
3.  In the upper-right corner of the page, click **Create Dashboard**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6139/15451055171565_en-US.png)

4.  Enter the name of the dashboard.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6139/15451055171566_en-US.png)

5.  Click **Create**. The page is automatically redirected to the new dashboard page where you can add various metric charts as needed.
6.  When you rest the pointer over the dashboard name, the **Edit** option appears on the right hand side. To modify the dashboard name, click **Edit**.

## Delete a dashboard {#section_l51_ryy_5db .section}

You can delete a dashboard if you do not need it given changes in your business operations.

**Note:** When you delete a dashboard, all charts that are added to the dashboards are also deleted.

Procedure

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Dashboard** \> **Custom Dashboard**.
3.  Select the target dashboard from the **Dashboards** drop-down list.
4.  In the upper-right corner of the page, click **Delete Dashboard** to delete the dashboard.

