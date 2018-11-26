# Receive alarm notifications through a DingTalk group {#concept_i4r_ftq_zdb .concept}

With the new function provided by CloudMonitor, you can receive alarm notifications through a DingTalk group by following the instructions provided in this topic.

For the existing alarm rules, you only need to add the webhook address of the DingTalk robot to your contact, eliminating the need to modify the rules.

After the DingTalk robot is added to an existing contact, all alert notifications that the contact previously receives through email and SMS can now be received through the DingTalk group.

## Create a DingTalk robot \(on your PC\) {#section_dk1_z5v_rfb .section}

1.  Open the DingTalk group through which you want to receive alarm notifications.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792721624_en-US.png)

2.  Click the **Group Settings** icon in the upper right corner. The Group Settings window is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792821626_en-US.png)

3.  Click **ChatBot**. The ChatBot dialog box is displayed. Click **Custom** to create a DingTalk robot for receiving alarm notifications.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792821627_en-US.png)

4.  In the Robot details dialog box, click **Add**. The Add Robot dialog box is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792821628_en-US.png)

5.  Enter the robot name, such as CloudMonitor alarm notification. Then, click **Finished**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792821631_en-US.png)

6.  Click **Copy** to copy the webhook address. Then, click **Finished** to add the robot.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792821632_en-US.png)


## Add a DingTalk robot to a contact {#section_xld_cvv_rfb .section}

You can add the webhook address of the created DingTalk robot to the alarm contact. Then, you can receive alarm notifications through the DingTalk group where the robot is created.

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left navigation pane, click **Alarm Contacts** under **Alarms**. The Alarm Contact Management page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792821662_en-US.png)

3.  Find a contact and click **Edit** to add the webhook address of the DingTalk robot in the Set Alarm Contact dialog box. Alternatively, click **Create Alarm Contact** to create a contact that uses the DingTalk robot.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/154322792821663_en-US.png)


