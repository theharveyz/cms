# Create an alarm template {#concept_znd_wpq_zdb .concept}

## Purpose {#section_fwb_cqq_zdb .section}

When your Alibaba Cloud account has many cloud product resources, such as servers, it is necessary to know how to quickly create and modify alarm rules for them. This topic provides a case to describe how enterprise users can use application groups and alarm templates to manage cloud resource alarm rules for various services.

## Use alarm templates to improve alarm rule configuration efficiency {#section_s35_kqq_zdb .section}

-   Differences between alarm rules configured for an application group and those configured for a single instance
    -   When creating an alarm rule, you can set the resource scope to "instance" or "application group". If you choose "application group", the alarm rule will be effective on all resources within the specified application group. If you want to scale your services, you only need to move resources into or remove resources from the application group without the need to add or delete alarm rules. If you modify an alarm rule, the rule will be effective on all instances within the application group after modification.
    -   If you create an alarm rule for a single instance, the rule will be effective only on the instance. If the rule is modified, the modification is also effective only on the instance. As the number of instances increases, managing alarm rules will become increasingly difficult.
-   How alarm templates improve alarm rule configuration efficiency
    -   The monitoring metrics and alarm thresholds of basic services, such as ECS, RDS, and SLB, are set to fixed values during alarm rule configuration. After creating a template for the metrics and thresholds, you only need to create an application group and apply the template to the group. By this means, you can create alarm rules with one click when your services grow.
    -   If you want to add, modify, or delete alarm rules in batches, you can modify the template and apply the template to the application group. This greatly saves time.

## Case {#section_gwb_cqq_zdb .section}

When there are many servers and other instances under your account, we recommended that you create different application groups for the resources by service, and then use the groups to manage the resources in batches.

The following uses the backend services of a common e-commerce company to shows how to create an application group and use an alarm template to quickly build a service monitoring and alarming system on the cloud.

## Procedure {#section_kwb_cqq_zdb .section}

1.  Create an alarm template named "EcommerceBackendAlarmTemplate".
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  From the left-side navigation pane, choose **Alarm Templates** \> **Alarms**.
    3.  On the Alarm Templates page, click **Create Alarm Template** in the upper-right corner.
    4.  In the displayed dialog box, set the parameters in the Basic Info area.
    5.  In the View Alarm Rules area, click Add Alarm Rule to add the required alarm rules to the alarm template.
    6.  Click **OK**.
2.  Create an alarm contact and an alarm contact group.
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  From the left-side navigation pane, choose **Alarms** \> **Alarm Contacts**.
    3.  On the Alarm Contact Management page, click **Create Alarm Contact** in the upper-right corner. In the displayed dialog box, enter your mobile phone number and email.

        To ensure that you can receive and verify alarm notifications in a timely manner, the system will send verification codes to your mobile phone and email.

    4.  Click the **Alarm Contact Group** tab.
    5.  In the upper-right corner, click **Create Alarm Contact Group**.
    6.  In the displayed dialog box, enter the group name and select the contacts that you want to add to the group.
3.  Create an application group and apply the alarm template. Here, we create an application group named "InventoryManagementOnlineEnvironment" and use the created alarm template "EcommerceBackendAlarmTemplate".
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, click **Application Groups**.
    3.  On the Application Groups page, click **Create Group** in the upper-right corner.
    4.  In the **Basic Information** area, set **Product Group Name** and **Contact Group**.

        The contact group is the alarm contact group for receiving alarm notifications.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6235/15441760105163_en-US.jpg)

    5.  In the **MonitorAlarm** area, set **Select Template** and **Notification Methods** and enable **Initialize Agent Installation**.

        The selected template is used to initialize alarm rules for the instances in the group. After new instances are created, a CloudMonitor agent will be automatically installed to collect monitoring data.

    6.  In the **Add Instance dynamically** area, add at most three dynamic rules with the relationship of AND or OR. Then, click **Add Product** to customize dynamic rules for RDS and SLB.

        Generally, the cloud resources used for inventory management are in the combination of "server+database+SLB resource". You can customize dynamic rules to add ECS instances. An ECS instance name can be matched through the condition of **Contain**, **startwith**, or **endwith**. The instances conforming to the dynamic rules will be added to the current application group \(including instances to be created in the future.\)

    7.  Click **Create Application Group**.

        The instances conforming to the dynamic rules are added to the created application group, which can be viewed on the Basic Information page of the application group.


