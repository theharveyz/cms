# Agent introduction {#concept_rfs_thv_vdb .concept}

## Installation path {#section_lct_qk2_xdb .section}

-   Linux：/usr/local/cloudmonitor
-   Windows 64-bit:  C:\\Program Files \(x86\)\\Alibaba\\cloudmonitor
-   Windows 32-bit: C:\\Program Files\\Alibaba\\cloudmonitor

## Process Information {#section_ow1_rq2_xdb .section}

After the host monitor plug-in is installed, you will run the following two processes on your server:

-   /usr/local/cloudmonitor/jre/bin/java
-   /usr/local/cloudmonitor/wrapper/bin/wrapper

## Port description {#section_z3f_vq2_xdb .section}

-   Listen on the TCP localhost 32000 port for the process daemon.
-   Access the TCP localhost 32000 port for the process daemon.
-   Access TCP remote port 3128, 8080, 443. Used for heartbeat and monitoring data reporting, non-Ali cloud machines use 443 ports, the Ali cloud machine uses either port 3128 or port 8080.
-   Access the HTTP remote 80 port for cloud monitoring plug-in upgrades.

## Plug-in log {#section_gkl_wq2_xdb .section}

-   The monitoring data acquisition log is located at/usr/local/cloudmonitor/logs 
-   Startup, shutdown, process daemon and other logs are located at /usr/local/cloudmonitor/wrapper/logs 。
-   You can modify/usr/local/cloudmonitor/config/log4j.properties  to adjust the log level.

## Resource footprint {#section_mmw_252_xdb .section}

-   /usr/local/cloudmonitor/wrapper/bin/wrapper process occupies about 1 m of memory, basically does not consume the CPU.
-   /usr/local/cloudmonitor/Barre/bin/Java Process occupies about 70 m of memory and single-core 1-2% CPU.
-   Installation Package 70 m, approximately 200 m disk space after installation is completed.
-   The log takes up to 40 m space and more than 40 m is cleared.
-   Monitor data is sent every 15 seconds, and the bandwidth of the internal network is approximately 10kb.
-   Send heartbeat data every 3 minutes, which occupies approximately 2kb of network bandwidth.

## External dependencies {#section_x3b_lw2_xdb .section}

-   The cloud monitoring agent is written in the Java language and is built in With Barre 1.8.
-   Java service wrapper is used for process daemon, boot startup, Windows Service Registration, and so on.
-   The `iproute ss` command is used to capture a TCP connection, and if the current system does not, the user needs to install it himself

## Installation instructions {#section_yhh_xw2_xdb .section}

See [EN-US\_TP\_6156.md\#](intl.en-US/User Guide/Host monitoring/Install CloudMonitor agent.md#).

## Non-Ali cloud host Installation Method {#section_a12_cx2_xdb .section}

1.  Log in to the cloud monitoring [host monitoring](https://cms.console.aliyun.com/#/hostmonitor/host) page.
2.  After clicking on the upper right corner of the page, **how to add hosts** and open the document, after you copy the plug-in installation command for a non-Ali cloud server, you can just execute it on the machine.

