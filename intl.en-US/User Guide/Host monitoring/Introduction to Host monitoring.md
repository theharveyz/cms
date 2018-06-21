# Introduction to Host monitoring {#concept_ypb_thv_vdb .concept}

The host monitoring service of CloudMonitor allows you to install an agent on your servers to monitor the server system.  Currently, host monitoring supports Linux and Windows operating systems.

## Scenarios {#section_oyy_3rx_wdb .section}

Host monitoring can provide support to the Alibaba Cloud ECS servers, as well as the servers or physical machines of other vendors.  Host monitoring collects statistics using a diverse range of OS-related metrics, allowing you to request for the server resource usage and obtain metric data for troubleshooting.

## Hybrid cloud monitoring solution {#section_ufm_lrx_wdb .section}

CloudMonitor agent collects server metric data. You can install the agent on a non-ECS server for basic monitoring, on and off the cloud.

## Enterprise-level monitoring solution {#section_q3d_hcd_xdb .section}

Host monitoring also provides the application groups function. This function allows you to allocate servers to the different regions of Alibaba Cloud \(to the same group\) for server management from the business perspective.  Host monitoring supports group-based alarm management. You need to configure only one alarm rule for the entire group. This will greatly improve O&M efficiency and overall management experience.

**Note:** 

-   Host monitoring supports Linux and Windows, but does not support Unix.

-   Server resource consumption of the agent: The CloudMonitor agent installation package is 75 MB. After installation, the size of the package becomes 200 MB with 64-MB memory usage, which is smaller than 1% CPU usage.

-   Root permission is required for Agent installation.

-   The TCP status statistics function is similar to the Linux netstat -anp command. When many TCP connections exist, a large amount of CPU time is consumed. Therefore, this function is disabled by default.

    a. To enable this function in Linux, set “netstat.tcp.disable” in the “cloudmonitor/config/conf.properties” configuration file to “false”.  Restart the agent once you modify the configuration.

    To enable this function in Windows, set “netstat.tcp.disable” in the “C:\\Program  Files\\Alibaba\\cloudmonitor\\config” configuration file to “false”.  Restart the agent once you modify the configuration.


## Monitoring capability {#section_vrr_4cd_xdb .section}

CloudMonitor allows more than 30 metrics covering CPU, memory, disk, and network to meet the basic monitoring and O&M requirements of the servers. Click [here](intl.en-US/User Guide/Host monitoring/Host monitoring metrics.md#) to view the full list of metrics.

## Alarm capability {#section_cy1_xcd_xdb .section}

CloudMonitor provides alarm service for all metrics, allowing you to set alarm rules for individual servers, application groups, and all the other resources. You can use the alarm service as per your business requirements.

You can use the alarm service directly in the host monitoring list, or use it in your application group once you add servers to the group.

