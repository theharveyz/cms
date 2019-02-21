# CloudMonitor Java agent introduction {#concept_rfs_thv_vdb .concept}

CloudMonitor provides you with a powerful host monitoring agent that allows you to monitor your servers systematically. The following is a brief introduction to this service, including its installation and resource usage.

## Installation path {#section_lct_qk2_xdb .section}

-   Linux: /usr/local/cloudmonitor
-   Windows: C:\\Program Files\\Alibaba\\cloudmonitor

## Process information {#section_ow1_rq2_xdb .section}

After an agent is installed, the following two processes run on your server:

-   /usr/local/cloudmonitor/jre/bin/java
-   /usr/local/cloudmonitor/wrapper/bin/wrapper

## Port description {#section_z3f_vq2_xdb .section}

-   TCP port 32000 of the local host is accessed and listened to for daemons.
-   TCP port 3128, 8080, or 443 of remote servers is accessed for heartbeat monitoring and monitoring data reporting. Port 3128 or 8080 is used for Alibaba Cloud hosts, and port 443 is used for other hosts.
-   HTTP port 80 of remote servers is accessed for CloudMonitor agent upgrades.

## Agent logs {#section_gkl_wq2_xdb .section}

-   Logs of monitoring data are located at /usr/local/cloudmonitor/logs.
-   Logs of startup, shutdown, and daemons are located at /usr/local/cloudmonitor/wrapper/logs.
-   You can modify /usr/local/cloudmonitor/config/log4j.properties to adjust the log level.

## Resource usage {#section_mmw_252_xdb .section}

-   The process /usr/local/cloudmonitor/wrapper/bin/wrapper occupies about 1 MB of memory with little to no CPU usage.
-   The process /usr/local/cloudmonitor/jre/bin/java occupies about 70 MB of memory and 1% to 2% of one core's CPU usage.
-   The installation package is 70 MB and occupies about 200 MB of disk space after the installation is complete.
-   Logs use a maximum space of 40 MB and are cleared if they use more than 40 MB.
-   Monitoring data is sent every 15 seconds, occupying about 10 KB intranet bandwidth.
-   Heartbeat data is sent every three minutes, occupying about 2 KB intranet bandwidth.

## External dependencies {#section_x3b_lw2_xdb .section}

-   The Java agent of CloudMonitor is built in with JRE 1.8.
-   Java service wrapper is used for daemons, start up at boot, and Windows service registration.
-   The `ss -s` command is used to capture a TCP connection, and if you do not have this command in the current system, you must install iproute yourself.

## Installation instructions {#section_yhh_xw2_xdb .section}

See [Install CloudMonitor Java agent](reseller.en-US/User Guide/Host monitoring/Install CloudMonitor Java agent.md#).

## Install an agent on a host not provided by Alibaba Cloud {#section_a12_cx2_xdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, click **Host Monitoring**.
3.  At the top of the displayed page, click **Not Aliyun ecs install**. In the **Monitor Install Guide** dialog box that is displayed, select the agent type and host type to view the corresponding installation method.

