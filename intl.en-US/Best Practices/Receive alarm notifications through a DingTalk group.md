# Receive alarm notifications through a DingTalk group {#concept_i4r_ftq_zdb .concept}

With the new function provided by CloudMonitor, you can receive alarm notifications through a DingTalk group by following the instructions provided in this topic.

For the existing alarm rules, you only need to add the webhook address of the DingTalk robot to your contact with no need to modify the rules.

1.  Create a DingTalk robot \(on your PC\)
    1.  Open the DingTalk group through which you want to receive alarm notifications.
    2.  In the upper right corner of the group chat window, click Group Settings.
    3.  Click ChatBot. In the displayed dialog box, click Custom to customize a chatbot for receiving alarm notifications.
    4.  In the displayed Robot details dialog box, click **Add**.
    5.  In the displayed Add Robot dialog box, enter the chatbot name, for example, CloudMonitor alarm notification, and click **Finished**.
    6.  Click Copy to copy the webhook address and click Finished.
2.  Add the chatbot to the alarm contact

    You can add the webhook address of the created chatbot to the alarm contact. Then, you can receive alarm notifications through the DingTalk group where the chatbot is created.

    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left navigation pane, click **Alarm Contacts** under **Alarms**. The Alarm Contact Management page is displayed.

        ![](images/5203_en-US.png)

    3.  On the Alarm Contact Management page, locate a contact and click **Edit** to add the webhook address of the chatbot. Alternatively, click **Create Alarm Contact** to create a contact that uses a chatbot.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6237/15432268985204_en-US.jpg)


After the chatbot is added to an existing contact, all alert notifications the contact previously receives through email and SMS can now be received through the DingTalk group.

