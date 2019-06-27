# Metrics {#concept_gdq_tgc_5db .concept}

Host monitoring metrics include the metrics that a CloudMonitor agent monitors and the ECS basic metrics. The CloudMonitor agent collects monitoring data at a 15-second interval. CloudMonitor also collects monitoring data of ECS basic metrics at a 1-minute interval.

**Note:** The ECS basic monitoring data may be different from the monitoring data that the CloudMonitor agent collects due to the following reasons:

-   Different monitoring frequencies: the monitoring data displayed on monitoring charts is the average value of the data collected during one statistical period. The statistical period for ECS basic monitoring data is one minute. The statistical period for monitoring data that the agent collects is 15 seconds. In the case of large monitoring data fluctuations, the value of ECS basic monitoring data is smaller than that of monitoring data that the agent collects due to load shifting.
-   Different monitoring targets: the network traffic data collected by means of ECS basic metrics monitoring is used for billing. The data does not include the free traffic between ECS instances and Server Load Balancer \(SLB\) instances. However, the network traffic data collected by the agent indicates the actual network traffic of each network interface card \(NIC\). Therefore, the network traffic data collected by the agent is greater than that collected by means of ECS basic metrics monitoring. In this case, the data that the agent collects is greater than the actually purchased bandwidth or traffic quota.

## Metrics collected by the CloudMonitor agent {#section_an5_yjd_xdb .section}

-    **CPU metrics** 

    You can run the top command in Linux to understand the metrics listed in the following table.

    |Metric|Description|Unit|Remarks|
    |:-----|:----------|:---|:------|
    |Host.cpu.idle|The percentage of CPU currently not utilized.|%|Indicates the percentage of CPU currently in the idle status.|
    |Host.cpu.system|The percentage of CPU currently occupied by the kernel.|%|Measures the CPU occupied by a system context switch. A high value indicates that many processes or threads are running on the host.|
    |Host.cpu.user|The percentage of CPU currently occupied by user processes.|%|Measures the CPU occupied by user processes.|
    |Host.cpu.iowait|The percentage of CPU currently waiting for I/O operations.|%|A high value indicates frequent I/O operations.|
    |Host.cpu.other|The percentage of CPU occupied by other operations.|%|Calculation method: CPU usage of Nice + CPU usage of SoftIrq + CPU usage of Irq + CPU usage of Stolen.|
    |Host.cpu.totalUsed|The percentage of CPU currently occupied.|%|The sum of the preceding CPU consumption. This metric is usually used for alarm purposes.|

-    **Memory metrics** 

    You can run the free command in Linux to understand the metrics listed in the following table. Data source: /proc/meminfo. CloudMonitor uses the GlobalMemoryStatusExAPI function to collect Windows system data.

    |Metric|Description|Unit|Remarks|
    |:-----|:----------|:---|:------|
    |Host.mem.total|Total memory.|Byte| The total memory of the host.

 Data source: MemTotal in the /proc/meminfo directory.

 |
    |Host.mem.free|The amount of unused memory.|Byte| The amount of available memory in the system.

 Data source: MemFree in the /proc/meminfo directory.

 |
    |Host.mem.used|The amount of memory in use.|Byte| The amount of used memory in the system.

 Calculation method: total - free.

 |
    |Host.mem.actualused|The memory actually used by the user.|Byte|Calculation method:     -   When MemAvailable exists in the /proc/meminfo directory: total - MemAvailable.
    -   When MemAvailable does not exist in the /proc/meminfo directory: used - buffers - cached.
 CentOS 7.2, Ubuntu 16.04, and later versions use the new Linux kernel. These versions provide more accurate memory estimation. For more information about the description of the MemAvailable column about the kernel, see [commit](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=34e431b0ae398fc54ea69ff85ec700722c9da773).

 |
    |Host.mem.freeutilization|The percentage of available memory.|%|Calculation method:     -   When MemAvailable exists in the /proc/meminfo directory: MemAvailable/total × 100%.
    -   When MemAvailable does not exist in the /proc/meminfo directory: \(total - actualused\)/total × 100%.
 |
    |Host.mem.usedutilization|The memory usage.|%|Calculation method:     -   When MemAvailable exists in the /proc/meminfo directory: \(total - MemAvailable\)/total × 100%.
    -   When MemAvailable does not exist in the /proc/meminfo directory: \(total - free - buffers - cached\)/total × 100%.
 |

-    **Metrics of average system loads** 

    You can run the top command in Linux to understand the metrics listed in the following table. A higher value of a metric indicates a busier system.

    |Metric|Description|Unit|
    |:-----|:----------|:---|
    |Host.load1|The average system loads over the past one minute. This metric is not available for Windows operating systems.|None.|
    |Host.load5|The average system loads over the past five minutes. This metric is not available for Windows operating systems.|None.|
    |Host.load15|The average system loads over the past 15 minutes. This metric is not available for Windows operating systems.|None.|

-    **Disk metrics** 

    -   You can run the df command in Linux to understand the disk usage and inode usage metrics.
    -   You can run the iostat command in Linux to understand the disk read/write metrics.
    |Metric|Description|Unit|
    |:-----|:----------|:---|
    |Host.diskusage.used|The space of the disk in use.|Byte|
    |Host. disk. utilization|The disk usage.|%|
    |Host.diskusage.free|The remaining storage space of the disk.|Byte|
    |Host.diskussage.total|The total disk storage.|Byte|
    |Host.disk.readbytes|The number of bytes per second read from the disk.|Byte/s|
    |Host.disk.writebytes|The number of bytes per second written to the disk.|Byte/s|
    |Host.disk.readiops|The number of read requests per second received by the disk.|Request/s|
    |Host.disk.writeiops|The number of write requests per second received by the disk.|Request/s|

-    **File system metrics** 

    |Metric|Description|Unit|Remarks|
    |:-----|:----------|:---|:------|
    |Host.fs.inode|Inode usage.|%|This metric is not available for Windows operating systems. Linux and UNIX systems use inode numbers, instead of file names, to identify files. When you have used up inode numbers, you cannot create new files even if some disk space is available. Therefore, CloudMonitor must monitor the inode usage. The number of inodes indicates the number of files. A large number of small files can cause a high inode usage.|

-    **Network metrics** 

    -   You can run the iftop command in Linux to understand the network metrics. You can run the ss command in Linux to understand the metrics of TCP connection data.
    -   The system collects the following TCP connection data by default: TCP\_TOTAL \(the total number of connections\), ESTABLISHED \(the number of established connections\), and NON\_ESTABLISHED \(the number of connections not in established status\). To obtain such data, follow these steps:
        -   Linux

            Change the value of `netstat.tcp.disable` in the cloudmonitor/config/conf.properties configuration file to `false` to collect the data. Afterward, restart the CloudMonitor agent.

        -   Windows

            Change the value of `netstat.tcp.disable` in the C:\\”Program Files”\\Alibaba\\cloudmonitor\\config configuration file to `false` to collect the data. Afterward, restart the CloudMonitor agent.

    |Metric|Description|Unit|
    |:-----|:----------|:---|
    |Host.netin.rate|The number of bits per second received by the NIC. This is the upstream bandwidth of the NIC.|Bit/s|
    |Host.netout.rate|The number of bits per second sent by the NIC. This is the downstream bandwidth of the NIC.|Bit/s|
    |Host.netin.packages|The number of packets per second received by the NIC.|Packet/s|
    |Host.netout.packages|The number of packets per second sent by the NIC.|Packet/s|
    |Host.netin.errorpackage|The number of incoming error packets detected by the drive.|Packet/s|
    |Host.netout.errorpackages|The number of outgoing error packets detected by the drive.|Packet/s|
    |Host.tcpconnection|The number of TCP connections in various statuses, including LISTEN, SYN\_SENT, ESTABLISHED, SYN\_RECV, FIN\_WAIT1, CLOSE\_WAIT, FIN\_WAIT2, LAST\_ACK, TIME\_WAIT, CLOSING, and CLOSED.| |

-    **Process metrics** 

    -   You can run the top command in Linux to understand the CPU usage and memory usage of processes. The CPU usage indicates the consumption of multi-core CPUs.
    -   You can run the lsof command in Linux to understand Host.process.openfile.
    -   You can run the ps aux |grep ‘Keyword’ command to understand Host.process.number.
    |Metric|Description|Unit|Remarks|
    |:-----|:----------|:---|:------|
    |Host.process.cpu|The CPU usage of a process.|%|You cannot specify alarms for this metric.|
    |Host.process.memory|The memory usage of a process.|%|You cannot specify alarms for this metric.|
    |Host.process.openfile|The number of files opened by the current process.|File|You cannot specify alarms for this metric.|
    |Host.process.number|The number of processes that match the specified keyword.|Process|You cannot specify alarms for this metric.|


## ECS basic metrics {#section_gxh_1nd_xdb .section}

If your host is an ECS instance, CloudMonitor automatically monitors the metrics listed in the following table after you purchase the ECS instance. You do not need to install the CloudMonitor agent to monitor these metrics. CloudMonitor collects ECS basic metrics at a 1-minute interval.

|Metric|Description|Unit|
|:-----|:----------|:---|
|ECS.CPUUtilization|CPU usage.|%|
|ECS.InternetInRate|The average rate of inbound Internet traffic.|Bit/s|
|ECS.IntranetInRate|The average rate of inbound intranet traffic.|Bit/s|
|ECS.InternetOutRate|The average rate of outbound Internet traffic.|Bit/s|
|ECS.IntranetOutRate|The average rate of outbound intranet traffic.|Bit/s|
|ECS.SystemDiskReadbps|The number of bytes per second read from the system disk.|Byte/s|
|ECS.SystemDiskWritebps|The number of bytes per second written to the system disk.|Byte/s|
|ECS.SystemDiskReadOps|The number of reads per second from the system disk.|Time/s|
|ECS.SystemDiskWriteOps|The number of writes per second to the system disk.|Time/s|
|ECS.InternetIn|Inbound Internet traffic.|Byte|
|ECS.InternetOut|Outbound Internet traffic.|Byte|
|ECS.IntranetIn|Inbound intranet traffic.|Byte|
|ECS.IntranetOut|Outbound intranet traffic.|Byte|

