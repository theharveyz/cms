# Monitor the intranet {#concept_cxr_lky_5db .concept}

## Scenario {#section_gj1_ggt_zdb .section}

As more and more users migrate their instances from classic networks to VPCs \(for higher security and reliability\), effective monitoring systems are required to determine whether internal VPC services are working properly. This topic shows how to monitor the availability of services on ECS, the connectivity of ECS to RDS and Redis, and the responsiveness of SLB in a VPC.

## Principle {#section_hj1_ggt_zdb .section}

First, you need to install a CloudMonitor agent on your server. Then, you need to create monitoring tasks in the CloudMonitor console, select the server on which the agent is installed as the detection source, and configure the target URL or port. The detection source then sends an HTTP request or a Telnet request to the target URL or port every minute through the agent. The detection source also collects the response time and status codes and sends them to CloudMonitor for alarm and display.

## Monitor the intranet {#section_mfp_lgt_zdb .section}

-   Prerequisites
    -   The CloudMonitor agent has been installed on the detection source.
    -   You have created an application group and added the detection source to the group.

-   Procedure
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, click **Application Groups**.
    3.  On the Application Groups page, click the application group for which you want to create an availability monitoring task.
    4.  In the left-side navigation pane, click **Availability Monitoring**.
    5.  In the upper-right corner, click **Create Configuration**.
        -   To monitor the responsiveness of a local ECS process in a VPC, select the target ECSs to be monitored as **Target Server** and enter the addresses in localhost:port/path format as **Detection Target**.
        -   To monitor the responsiveness of the SLB in a VPC, select an ECS that is located in the VPC as **Target Server** and enter the SLB address as **Detection Target**.
        -   To monitor the responsiveness of the RDS or Redis used in the ECS backend in a VPC, add the RDS or Redis in the VPC to the application group, select the corresponding ECS as **Target Server**, and select RDS or Redis instances as **Detection Target**.
    6.  Click **OK**. Then, you can view the detection results in the corresponding monitoring chart of the task. If detection fails, you will receive an alarm notification.
    7.  Click **Monitoring Charts** of a task to view the monitoring details.

