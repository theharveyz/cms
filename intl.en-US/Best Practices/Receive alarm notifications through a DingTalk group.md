# Receive alarm notifications through a DingTalk group {#concept_i4r_ftq_zdb .concept}

CloudMonitor provides an alarm notification function that sends notifications to a specific DingTalk group. The process is described in this topic.

For existing alarm rules, you only need to add the webhook address of the DingTalk robot to your contacts. You do not need to modify any rules.

After the webhook address is added to an existing contact, all alarm notifications that you previously received by email and SMS are now received through the DingTalk group.

## Create a DingTalk robot \(PC\) {#section_dk1_z5v_rfb .section}

1.  Open the DingTalk group for which you want to receive alarm notifications.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606021624_en-US.png)

2.  In the upper-right corner, click the **Group Settings** icon and choose **ChatBot**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606121626_en-US.png)

3.  In the ChatBot dialog box, click **Custom**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606121627_en-US.png)

4.  In the Robot details dialog box, click **Add**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606121628_en-US.png)

5.  In the Add Robot dialog box, enter a name for the robot, for example, CloudMonitor alarm notification, and click **Finished**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606121631_en-US.png)

6.  Click **Copy** and then click **Finished**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606121632_en-US.png)


## Add a DingTalk robot to your alarm contacts {#section_xld_cvv_rfb .section}

You can add the webhook address of the created DingTalk robot to your alarm contacts so that you can receive alarm notifications from the DingTalk group where the robot is created.

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  From the left-side navigation pane, choose **Alarms** \> **Alarm Contacts**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606121662_en-US.png)

3.  On the Alarm Contact Management page, find the target contact and click **Edit**. In the Set Alarm Contact dialog box, add the webhook address of the DingTalk robot. Alternatively, click **Create Alarm Contact** to create a contact who needs to use the DingTalk robot.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154417606121663_en-US.png)


