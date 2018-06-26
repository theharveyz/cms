# Event monitoring best practices {#concept_cxr_lky_5db .concept}

## Scenario {#section_gj1_ggt_zdb .section}

As more and more users migrate from the classic network to the VPC network environment with high security and reliability, how to monitor the responsiveness of internal VPC services becomes a concern for users. The following describes how to monitor the availability of services on ECS, the connectivity of ECS to RDS and Redis, and the responsiveness of SLB in a VPC through specific cases.

## Principles {#section_hj1_ggt_zdb .section}

First, you must install the CloudMonitor agent on the server. Then, you can configure the monitoring task on the console, select the computer on which the agent has been installed as the test source, and configure the target URL or port to be tested. Once configured, the computer used as the test source sends an HTTP request or Telnet request to the target URL or port every minute through the agent, and collects the response time and status codes to CloudMonitor for alarms and chart display.

## Operation instructions {#section_mfp_lgt_zdb .section}

-   Prerequisites
    -   + The CloudMonitor agent must be installed on the server used as the test source.
    -   + You must create an application group and add the computer used as the test source to the group.

-   Procedure

    1.  Log in to the cloud monitor console and select the application grouping on the left-hand menu of the page.
    2.  2. Select the application group for which you want to create an availability monitoring task, and enter the application group details page.
    3.  Select **Availability Monitoring** from the left-side navigation pane to go to the Availability Monitoring page.
    4.  Click Create Configuration in the upper-right corner of the page to go to the Create Local Health Check page.
        -   + To monitor the responsiveness of the local ECS process in VPC, you can select all the ECSs to be monitored in the test source, and enter the address in the format of "localhost:port/path" in the test target for local test.
        -   + To monitor the responsiveness of SLB in VPC, you can select an ECS in the same VPC network as SLB as the test source, and enter the address of SLB in the test target.
        -   + To monitor the responsiveness of RDS or Redis used in the ECS backend in VPC, you can add the RDS or Redis in the same VPC network as the ECS to the application group, select the corresponding ECS in the test source and select the RDS or Redis instance in the test target.
        -       5.  5. Click OK, and then you can view the test results in the corresponding monitoring chart of the task. An alarm notification is sent if the test fails.
    6.      Click Monitoring Chart in the task list to view the monitoring details.


