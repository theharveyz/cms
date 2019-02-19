# Introduction to the CloudMonitor GoLang agent {#concept_rfs_thv_vdb .concept}

This topic provides a brief introduction to the CloudMonitor GoLang agent and its installation and resource usage. The GoLang agent can enable you to monitor your servers in a centralized and systematic manner.

## Installation path {#section_lct_qk2_xdb .section}

-   Linux: /usr/local/cloudmonitor
-   Windows: C:\\Program Files\\Alibaba\\cloudmonitor

## Process information {#section_ow1_rq2_xdb .section}

After the agent is installed, the following two processes run on your server:

-   Linux 32-bit: CmsGoAgent.linux-386
-   Linux 64-bit: CmsGoAgent.linux-amd64
-   Windows 32-bit: CmsGoAgent.windows-386.exe
-   Windows 64-bit: CmsGoAgent.windows-amd64.exe

## Port description {#section_z3f_vq2_xdb .section}

-   TCP port 3128, 8080, or 443 of remote servers is accessed for heartbeat monitoring and the reporting of monitoring data. Port 3128 or 8080 is used for Alibaba Cloud hosts, and port 443 is used for other hosts.
-   HTTP port 80 of remote servers is accessed for CloudMonitor agent upgrades.

## Agent logs {#section_gkl_wq2_xdb .section}

-   Logs of monitoring data are stored in the log directory.
-   You can adjust the level of a log by modifying the `cms.log.level` field in the config/conf.properties file. If the field does not exist, you can manually create it. The level of a log can be DEBUG, INFO, WARNING, ERROR, or FATAL.

## Resource usage {#section_mmw_252_xdb .section}

-   The agent process occupies a memory of 10 to 20 MB and 1% to 2% of a single core CPU.
-   The size of the agent installation package is 10 to 15 MB.
-   Logs use up to 40 MB and are cleared if they use more than 40 MB.
-   Monitoring data is sent every 15 seconds, occupying about 10 KB of intranet bandwidth.
-   Heartbeat data is sent every 3 minutes, occupying about 2 KB of intranet bandwidth.

## Installation instructions {#section_yhh_xw2_xdb .section}

For details, see [Install CloudMonitor GoLang agent](reseller.en-US/User Guide/Host monitoring/Install CloudMonitor GoLang agent.md#).

## Install the agent on a host not provided by Alibaba Cloud {#section_a12_cx2_xdb .section}

1.  Log on to the [CloudMinitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Host Monitoring**.
3.  At the top of the displayed page, click **Not Aliyun ecs install**. In the **Monitor Install Guide** dialog box that is displayed, select the agent type and host type to view the corresponding installation method.

