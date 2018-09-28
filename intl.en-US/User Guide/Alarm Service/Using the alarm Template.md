# Using the alarm Template {#concept_bss_b45_vdb .concept}

The alert template function enables you to set and store the alert policies of the metrics of cloud products in templates. When creating alert policies, you can directly use alert templates without defining alert policies all over again. When your account has many cloud resources \(ECS, ApsaraDB for RDS, Server Load Balancer, and OSS\), it is recommended that you create application groups for these resources from the service perspective and then create and apply alert templates to the application groups. This provides a simple way of creating and maintaining alert policies.

To use the alert template function and application group function in combination, you can create alert templates and apply these templates to application groups so that alert policies can be quickly created for service modules.

By default, CloudMonitor provides an initialized alert template that contains the common alert metrics for ECS、RDS、SLB、CDN、Redis、Mongodb、OSS, allowing you to quickly start using the template.

**Note:** 

-   Alert templates can only be used with application groups. That is, alert templates are only applicable to alert policies with the resource range set to "Application Group".
-   Up to 100 alert templates can be created under each Alibaba Cloud account.
-   Each alert template can contain up to 30 metrics.
-   The alert template function only provides a shortcut to create alert policies. There is no one-to-one binding relationship between alert templates and alert policies. After an alert template is modified, the alert policies generated using this template remain unchanged. To modify the alert policies for an application group in batches, modify the corresponding alert template and apply the template to the application group.

## Creating or editing a template {#section_ttg_s45_vdb .section}

1.  Log in to the cloud monitor console and click on**Alarm service** \> **Alarm Template**Enter the alarm template page.
2.  At the upper-right corner of the page, click \*\*Create Alert Template\*\* to go to the page for creating an alert template.
3.  Fill out the alert template with the basic information, including the name and description, to facilitate subsequent management of the template and its purpose.
4.  Configure the alarm policy, click Add alarm rule, add rule description.
5.  Click confirm to save the template.

## Using the alarm Template {#section_kcs_dy5_vdb .section}

-   Apply an alert template to the application group to be created

    When you create an apply grouping for a resource, you can select the alarm template that is required to apply the grouping directly at the last step. After applying grouping creation success, cloud monitoring generates alarm rules for you to apply grouping dimensions according to the alarm template.

    ![](images/2647_en-US.png)

-   Apply an alert template directly to an application group

    If you have created an application group but have not created alert policies for the group, you can create an alert template and then quickly apply the template to the group.

    ![](images/2656_en-US.png)

-   Apply an alert template when creating alert policies

    To add alert policies to an application group, select "Application Group" for the resource range on the page for creating alert policies and then select "Create from Template" and the corresponding alert template during alert policy setup. This method enables quick creation of alert policies.

    ![](images/2662_en-US.png)


