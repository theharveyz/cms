# Why is my CPU usage in the CloudMonitor console displayed as 0%? {#concept_b1k_nvk_zdb .concept}

The reason that your CPU usage in the CloudMonitor console is displayed as 0% relates to how CPU usage is calculated in the CloudMonitor console. While ECS reports data to CloudMonitor once a minute, data shown in the console is the average of the previous five minutes of reported data. Therefore, if the average of every minute in the five minutes is less than 0.5%, then 0% will be displayed in the CloudMonitor console. As such, even if your CPU usage may be displayed as 0% in the CloudMonitor console, this does not necessarily mean that your actual CPU usage is at 0%, as it is more likely the case that your CPU usage is relatively low. As shown in the following monitoring chart, actual CPU usage for this user is around 0.5%, despite 0% being displayed on the console.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6269/15507304034963_en-US.jpg)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6269/15507304034964_en-US.jpg)

