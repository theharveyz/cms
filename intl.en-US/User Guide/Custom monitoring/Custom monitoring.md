# Custom monitoring {#concept_oq3_h3b_wdb .concept}

## Custom monitoring overview {#section_bdp_xmk_zdb .section}

Custom monitoring is a function that gives users the freedom to define monitoring items and alarm rules. You can monitor concerned services and report collected monitoring data to CloudMonitor in an agreed format through OpenAPI of CloudMonitor, so that CloudMonitor processes the data and generates alarms based on the result.

What is the difference between event monitoring and custom monitoring?

Event monitoring is used to resolve non-continuous event type data monitoring data reporting, querying, and warning scenarios. Custom monitoring scenario used to resolve periodic continuous acquisition of time series monitoring data reporting, querying and warning.

## Procedure {#section_fbb_ymk_zdb .section}

-   [Reporting Monitoring Data](intl.en-US/User Guide/Custom monitoring/Report monitoring data.md#)

-   query Monitoring Data

    Once the report of the monitored data is complete, you can view the data that has been reported in the console. You can view all monitoring data in custom monitoring, you can also go to a specified application group to view the relevant Custom monitoring data for this grouping

    -   View All custom Monitor Data
        1.  Log in to the cloud monitoring console and enter custom monitoring.
        2.  Select the corresponding application grouping and monitoring items to enter the time series details page.
        3.  Check the time series you want to view.

            ![](images/4922_en-US.png)

    -   View custom monitoring data under application grouping
        1.  Log in to the cloud monitoring console and enter the app grouping list page.
        2.  Select the appropriate application grouping to enter the grouping details page.
        3.  Click the Customize monitoring menu to go to the custom monitoring details page.
        4.  Select the appropriate monitoring item to enter the time series details page.
        5.  Check the time series you want to view.

            ![](images/4926_en-US.png)

-   Set alarm rules

    Custom monitoring provides you with the alarm function, and when you set up an alarm, you need to select the appropriate application grouping, when the alarm is triggered, a notification is sent to the contacts that apply the grouping. If the monitoring data you report requires an alarm, you can configure the alarm rules as follows.

    -   Mode one:

        1.  Log in to the cloud monitoring console and enter custom monitoring.
        2.  Select the corresponding application grouping and monitoring items to enter the time series details page.
        3.  Select the time series in which you want to create the alarm, and click set alarm rule in the action.
        4.  Enter the create alarm Rule Page, fill in the alarm rule name, set up the appropriate alarm policy and notification method.
    -   Mode two:

        1.  Log in to the cloud monitoring console and enter the app grouping list page.
        2.  Select the appropriate application grouping to enter the custom monitoring page within the app grouping. Select the time series for which you want to create the alarm rule, and in action, tap set alarm rule.
        3.  Go to the create alarm Rule Page, fill in the alarm rule name, select the appropriate monitoring item, dimension, alarm policy and notification method.

