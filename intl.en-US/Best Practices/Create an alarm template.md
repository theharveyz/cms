# Create an alarm template {#concept_znd_wpq_zdb .concept}

This topic illustrates how to use application groups and alarm templates to manage cloud resource alarm rules for various services more efficiently. These tactics are especially important for those who need to monitor and manage resources across several Alibaba Cloud products and regions and who need to modify alarm rules for these resources in a timely manner.

## Purposes {#section_s35_kqq_zdb .section}

-   Configuring alarm rules for application groups rather than for single instances can improve efficiency by greatly reducing the time required to configure alarm rules.
    -   By setting the resource range of an alarm rule to application group, your alarm rule will be effective for all resources within the target application group, and the number of resources monitored can expand as your services are scaled outward. After initial configuration, you can move specific resources into or out of the application group easily. You can also modify the alarm rule directly so to make changes effective to all instances within an application group.
    -   Conversely, setting the resource range to instance will make your alarm rule effective for only one instance. Modifications to your alarm rule will also be effective for only one instance. As a consequence, supposing that you set all your alarm rules this way, as the number of your instances increase, managing alarm rules for these instances will become increasingly time consuming and difficult.
-   Using alarm templates can also reduce the time required to configure alarm rules.

    The monitoring metrics and alarm thresholds of basic services, such as ECS, RDS, and SLB, are set to fixed values during alarm rule configuration. You can create alarm templates easily based on these configurations, and by creating alarm templates with your target metrics and condition thresholds, you can easily apply these templates to alarm rules you configure for an application group, making configuring rules easy even as your services scale outward. Using alarm templates also enables you to easily modify multiple alarm rules at the same time.


## Procedures {#section_gwb_cqq_zdb .section}

The following case outlines the procedure that can be applied to the typical back-end services of an e-commerce company. This case serves to illustrate how you can create application groups and use alarm templates to easily build a service monitoring and alarming system on the cloud, even for growing service requirements.

1.  Create an alarm template named "EcommerceBackendAlarmTemplate".
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  From the left-side navigation pane, choose **Alarm Templates** \> **Alarms**.
    3.  On the Alarm Templates page, click **Create Alarm Template** in the upper-right corner.
    4.  In the displayed dialog box, set the parameters in the Basic Info area.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6235/15529805115167_en-US.png)

    5.  In the View Alarm Rules area, click **Add Alarm Rule** to add the required alarm rules to the alarm template.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6235/15529805115169_en-US.png)

    6.  Click **OK**.
2.  Create an alarm contact and an alarm contact group.
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  From the left-side navigation pane, choose **Alarms** \> **Alarm Contacts**.
    3.  On the Alarm Contact Management page, click **Create Alarm Contact** in the upper-right corner. In the displayed dialog box, enter your phone number and email.

        To ensure that you can receive and verify alarm notifications in a timely manner, the system will send verification codes to your phone and email.

    4.  Click the **Alarm Contact Group** tab.
    5.  In the upper-right corner, click **Create Alarm Contact Group**.
    6.  In the displayed dialog box, enter the group name and select the contacts that you want to add to the group.
3.  Create an application group and apply the alarm template. Here, we create an application group named "InventoryManagementOnlineEnvironment" and use the created alarm template "EcommerceBackendAlarmTemplate".
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, click **Application Groups**.
    3.  On the Application Groups page, click **Create Group** in the upper-right corner.
    4.  In the **Basic Information** area, set **Product Group Name** and **Contact Group**.

        The contact group is the alarm contact group for receiving alarm notifications.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6235/15529805115163_en-US.jpg)

    5.  In the **MonitorAlarm** area, set **Select Template** and **Notification Methods** and enable **Initialize Agent Installation**.

        The selected template is used to initialize alarm rules for the instances in the group. After new instances are created, a CloudMonitor agent will be automatically installed to collect monitoring data.

    6.  In the **Add Instance dynamically** area, add at most three dynamic rules with the relationship of AND or OR. Then, click **Add Product** to customize dynamic rules for RDS and SLB.

        Generally, the cloud resources used for inventory management are a server, database, and SLB resource. You can customize dynamic rules to add ECS instances. An ECS instance name can be matched through the condition of **Contain**, **start with**, or **end with**. The instances conforming to the dynamic rules will be added to the specified application group \(including instances to be created in the future\).

    7.  Click **Create Application Group**.

        The instances conforming to the dynamic rules are added to the created application group, which can be viewed on the Basic Information page of the application group.


