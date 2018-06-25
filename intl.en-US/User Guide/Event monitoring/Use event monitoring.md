# Use event monitoring {#concept_idt_k3b_wdb .concept}

Event monitoring provides reporting, querying, and warning capabilities for event type data. You can conveniently collect and report exceptions or important changes in services to CloudMonitor, and receive alerts when exceptions occur.

![](images/4804_en-US.png)

What are the differences between event monitoring and custom monitoring?

Event monitoring is used when monitored data of non-continuous events is reported and queried, and alerts are generated. Custom monitoring is used when monitored data collected cyclically and continuously in the time series is reported and queried and alerts are generated.

## Process {#section_lhh_p2j_zdb .section}

-   Reporting event data

    See [EN-US\_TP\_6163.md\#](intl.en-US/User Guide/Event monitoring/Report event data.md#).


-   Querying event data

    Once you have finished reporting the event, you can view the data that has been reported in the console. You can view all the events in event monitoring, or you can enter a specific application grouping, view related events for this grouping.

    View all reported incidents:

    1.  Log in to the cloud monitoring console to enter event monitoring.
    2.  View all events, as shown in the following figure.

        ![](images/4816_en-US.png)

    3.  Click action View Details in to view the content of a specific event.![](images/4819_en-US.png)

        To query events of the specified group, go to the event monitoring page of the group.

-   Set alert policies.

     Set an alert rule Event monitoring provides the alerting function. When setting the alert rule, select the corresponding application group. After an alert is generated, a message is sent to all contacts in the group. If alerts must be generated for an reported event, configure the alert rule using the following methods:

    -   Method one:
        1.  Log in to the cloud monitoring console to enter event monitoring.
        2.  On the event list page, click **Create Alert Rule** next to an event.
        3.  Go to the alert rule creation page, enter the alert rule name, select the application group, and set the alert policy and notification mode.
    -   Method two:
        1.  Log in to the cloud monitoring console and enter the application cluster.
        2.  Select an application group and go to the \*\*Event Monitoring\*\* page of the group.
        3.  On the event list page, click \*\*Create Alert Rule\*\* next to an event.
        4.  Go to the alert rule creation page, enter the alert rule name and set the alert policy and notification mode.
    -   ![](images/4823_en-US.png)


