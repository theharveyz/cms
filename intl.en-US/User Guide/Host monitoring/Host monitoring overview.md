# Host monitoring overview {#concept_ypb_thv_vdb .concept}

The host monitoring service of CloudMonitor allows you to monitor your servers in a systematic manner by installing an agent on the servers. Host monitoring currently supports Linux and Windows Operating Systems \(OSs\).

## Scenarios {#section_oyy_3rx_wdb .section}

Host monitoring is available for both Alibaba Cloud ECS servers, and virtual and physical machines provided by other vendors.

Host monitoring collects statistics of a diverse range of OS-related metrics by using the agent, allowing you to retrieve the server resource usage and obtain metrics for troubleshooting.

## Hybrid cloud monitoring solution {#section_ufm_lrx_wdb .section}

Host monitoring uses the agent to collect server metrics. You can install the agent on an ECS server or a non-ECS server for monitoring on and off the cloud.

## Enterprise-level monitoring solution {#section_q3d_hcd_xdb .section}

Host monitoring also provides an application group function, which allows you to allocate servers from different regions of Alibaba Cloud to the same group for more efficient server management from a business operations perspective. Host monitoring supports group-based alarm management, meaning that you only need to configure one alarm rule for the entire group, which can improve O&M efficiency and the overall management experience.

**Note:** 

-   Host monitoring supports Linux and Windows, but does not support Unix.

-   Root permissions are required for the agent installation on a Linux OS and administrator permissions are required for that on a Windows OS.

-   The TCP status statistics function is similar to the Linux netstat -anp command. This function is disabled by default because a large portion of CPU time is consumed when many TCP connections exist.

-   To enable this function in Linux, set `netstat.tcp.disable` in the cloudmonitor/config/conf.properties configuration file to `false`. Restart the agent after you modify the configuration.
-   To enable this function in Windows, set `netstat.tcp.disable` in the C:\\Program Files\\Alibaba\\cloudmonitor\\config configuration file to `false`. Restart the agent after you modify the configuration.

## Monitoring capability {#section_vrr_4cd_xdb .section}

Host monitoring provides more than 30 metrics covering CPU, memory, disk, and network to meet your monitoring and O&M requirements. Click [here](reseller.en-US/User Guide/Host monitoring/Host monitoring metrics.md#) to view the full list of the metrics.

## Alarm capability {#section_cy1_xcd_xdb .section}

Host monitoring provides an alarm service for all metrics, allowing you to set alarm rules for instances, application groups, and all resources. You can use the alarm service according to your business requirements.

You can use the alarm service directly in the host monitoring list or apply the alarm rules to your application groups after you add servers into the groups.

