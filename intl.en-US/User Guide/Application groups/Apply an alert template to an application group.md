# Apply an alert template to an application group {#concept_bqc_1r3_mgb .concept}

This topic describes how to apply an alert template to an application group to quickly create alert rules for a business module.

## Background information {#section_p55_rmn_mgb .section}

If your account has a large amount of cloud resources such as ECS, RDS, SLB, and OSS instances, we recommend that you create service-related application groups and alert template and apply the alert templates to the application groups. This provides a simple way to create and maintain alert rules.

Alert templates must be used together with application groups. You can apply alert templates to application groups to quickly create alert rules for your business modules.

## Prerequisites {#section_mh4_1nn_mgb .section}

Before you apply an alert template to an application group, you must create an alert template. For more information about how to create an alert template, see [Use alarm templates](reseller.en-US/User Guide/Alarm service/Use alarm templates.md#).

## Procedure {#section_r4q_1nn_mgb .section}

**Precautions**

Alert templates must be used together with application groups. We recommend that you create application groups and alert templates for cloud resources based on your applications.

**Note:** After you apply an alert template to a specified group, CloudMonitor deletes the original alert rule for this group and create a new one based on the template.

**Procedure**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Application Groups**. The Application Groups page is displayed.
3.  Click the name of the group to which you want to apply the alert template. The group details page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/106915/155661217137619_en-US.png)

4.  Click **Apply Template to Group** in the upper-right corner. The Apply Template to Group page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/106915/155661217137620_en-US.png)

5.  Select an alert template and click **OK**.

