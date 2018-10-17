# Managing Site monitoring tasks {#concept_fwx_yjb_wdb .concept}

## Create a site monitoring task {#section_ygy_hqk_xdb .section}

The task of creating site monitoring is divided into three steps: Setting basic information, selecting Detection Points, and setting alarm rules. Set alarm rules to be optional and can not be set.

1.  Log in to the [cloud monitoring console](https://partners-intl.console.aliyun.com/#/cms)and select site administration from the menu on the left side of the page to monitor the site, enter the site monitoring task list page.
2.  Click the new task button in the upper-right corner of the page to enter the create site monitoring task page.
3.  Fill in the basic information.
    -   Monitoring type: Monitoring Protocol, HTTP \(s\) Enabled\), ping, TCP, UDP, DNS, SMTP, POP3, FTP 8 protocols.
    -   Task Name: the name of the monitoring task.
    -   Monitor address: The target monitor address can fill in more than one monitor address at a time, it is convenient for the user to set up in bulk. Multiple Monitor addresses are split into multiple tasks on Save.
    -   Monitor frequency: monitor cycle, for example, select a 1 minute frequency, the destination address is monitored at each geographic probe point at a frequency of 1 minute/times.
    -   Advanced Settings: different protocols support different advanced settings, and you can choose to use them according to the actual situation.
4.  Select a probe point
    -   Quick Selection of Detection Points: the common Detection Points will be packaged, so that you can choose quickly in bulk.
    -   Probe point advanced options: select the specified probe point on-demand.
5.  Set alarm rules
    -   Availability: divided into two options: the number of available points and the percentage of available points. Not available when the status code in the probe result is greater than 399. Number of available probe points = the number of probe results with a status code of less than 400 during a cycle, available probe points % = number of probe results within one cycle \(the probe point's status code is less than 400\) /total number of probe results\) \* 100.
    -   Average response time: the average response time for all probe points in each monitoring cycle.
    -   Alarm after several consecutive exceeds threshold: the actual monitoring value reaches the set threshold several times in succession before the alarm is made. This item is used to filter the occasional volatility of the monitoring data.
    -   Select Contact Group: The receiving object when sending the alarm notification.
    -   Alarm notification method: the sending channel of alarm notification.
    -   Advanced Settings: includes channel silence time, effective time, alarm callbacks.

## Modify site monitoring tasks {#section_yws_yqk_xdb .section}

1.  Log in to the [cloud monitoring console](https://partners-intl.console.aliyun.com/#/cms) and select site administration from the menu on the left side of the page to monitor the site, enter the site monitoring task list page.
2.  Select the task that needs to be modified, and click the modify button in the action.
3.  Go to the modify page and modify the corresponding content.

## Delete site monitoring task {#section_idr_brk_xdb .section}

1.  Log in to the [cloud monitoring console](https://partners-intl.console.aliyun.com/#/cms) and select site administration from the menu on the left side of the page to monitor the site, enter the site monitoring task list page.
2.  Select the task that needs to be modified, click the delete button in the action to delete the task.
3.  When the task is deleted, the associated alarm rules are deleted in sync.

## Enable or disable site monitoring tasks {#section_cks_2rk_xdb .section}

1.  Log in to the [cloud monitoring console](https://partners-intl.console.aliyun.com/#/cms) and select site administration from the menu on the left side of the page to monitor the site, enter the site monitoring task list page.
2.  Select the tasks that need to be enabled or disabled, click the enable or disable button in the action, enable or disable tasks.

