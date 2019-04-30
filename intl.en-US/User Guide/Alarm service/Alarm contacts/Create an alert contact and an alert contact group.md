# Create an alert contact and an alert contact group {#concept_rwl_xcs_ngb .concept}

This topic describes how to create an alert contact and an alert contact group, and add the contact to the group. With this configuration, contacts in the alert contact group can receive alert notification.

## Background information {#section_slq_1ds_ngb .section}

CloudMonitor sends alert notification based on alert contacts and contact groups. To receive alert notification, you must first create an alert contact and an alert contact group, add the contact to the contact group, and then select the contact group when creating an alarm rule.

An alert contact group is a group of one or more alert contacts. An alert contact can be added to multiple alert contact groups. In alert rule configurations, alert notification receivers are alert contact groups, not alert contacts.

## Prerequisites {#section_yzr_1ds_ngb .section}

An alert contact is created and the contact information is correct.

## Procedure {#section_dmt_1ds_ngb .section}

 **Precautions** 

**Note:** 

You must verify the email address to ensure that it can receive alert notification.

 **Create an alert contact** 

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Contact**. The Alarm Contact Management page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/116866/155660839037869_en-US.png)

3.  ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/116866/155660839037870_en-US.png)

4.  Click **Create Alarm Contact** in the upper-right corner. In the dialog box that appears, enter your name and email address.
5.  After the information is verified, click **Save**.

 **Create an alert contact group** 

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Contact**. The Alarm Contact Management page is displayed.
3.  Click the **Alarm Contact Group** tab.
4.  On the tab that appears, click **Create Alarm Contact Group** in the upper-right corner. The Create Alarm Contact Group dialog box is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/116866/155660839037871_en-US.png)

5.  Enter the group name, select the contacts to be added to the group, and click **OK**.

 **Add multiple contacts to a contact group** 

1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Contact**. The Alarm Contact Management page is displayed.
3.  Select the contacts that you want to add from the alert contact list.
4.  Click **Add to a Contact Group** at the bottom of the list.
5.  In the dialog box that appears, select a contact group and click **OK**.

