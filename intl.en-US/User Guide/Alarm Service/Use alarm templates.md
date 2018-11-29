# Use alarm templates {#concept_bss_b45_vdb .concept}

The alarm template function allows you to store the alarm rule settings of the metrics of cloud products into templates. When creating alarm rules, you can directly use alarm templates without defining alarm rules repeatedly. When your account has many cloud resources \(ECS, ApsaraDB for RDS, Server Load Balancer, and OSS\), it is recommended that you create application groups for these resources by service and then create and apply alarm templates to the application groups. This greatly simplifies the creation and maintenance alarm rules.

Alarm templates must be used along with application groups. You can create alarm templates and apply these templates to application groups, so that alarm rules can be quickly created for service modules.

By default, CloudMonitor provides an initialized alarm template that contains the common alarm metrics for ECS, ApsaraDB for RDS, Server Load Balancer, CDN, ApsaraDB for Redis, ApsaraDB for MongoDB, and OSS, allowing you to quickly start using the template.

**Note:** 

-   Alarm templates can only be used with application groups, that is, alarm templates apply only to alarm rules whose resource range is set to "Application Group".
-   Up to 100 alarm templates can be created under each Alibaba Cloud account.
-   Each alarm template can contain up to 30 metrics.
-   The alarm template function only provides a shortcut to create alarm rules. There is no one-to-one binding relationship between alarm templates and alarm rules. After an alarm template is modified, the alarm rules generated using this template remain unchanged. To modify the alarm rules for an application group in batches, modify the corresponding alarm template and apply the template to the application group.

## Create or edit an alarm template {#section_ttg_s45_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left navigation pane, click **Alarm templates** under **Alarms**. The Alarm templates page is displayed.
3.  In the upper-right corner of the page, click **Create Alarm Template**. The Create Alarm Template page is displayed.
4.  EnterTemplate Name and Description in the **Basic Info** area to make it easy to manage the template and its usage.
5.  Configure**Alarm Rules**. Click **Add Alarm Rule** to add rule description.
6.  Click **OK**to save the template.

## Use an alarm template {#section_kcs_dy5_vdb .section}

-   Apply an alarm template to the application group to be created

    When you create an application group for a resource, you can select the alarm template to be applied directly to the application group at the last step. After the application group is created, CloudMonitor generates alarm rules for the application group according to the alarm template.

-   Apply an alarm template directly to an application group

    If you have created an application group but have not created alarm template for the group, you can create an alarm template and directly apply the template to the group.

-   Apply an alarm template when creating alarm rules

    To add alarm rules to an application group, select "Application Group" for the resource range on the alarm rule creating page, and then select "Create from Template" and the corresponding alarm template during alarm rule setting. This method can create alarm rules quickly.


