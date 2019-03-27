# Host monitoring metrics {#concept_gdq_tgc_5db .concept}

Host monitoring metrics include agent-collected metrics and ECS basic metrics. Agent-collected metrics are monitored by the CloudMonitor agent and monitoring data is collected every 15 seconds. The monitoring data of ECS basic metrics is collected every minute.

**Note:** The ECS basic monitoring data may be inconsistent with the agent-collected monitoring data mainly because of the following reasons:

-   Different monitoring frequencies

    The monitoring data displayed on monitoring charts is the average value of the data collected during one statistical period. The statistical period of ECS basic monitoring data is one minute, whereas the statistical period of agent-collected monitoring data is 15 seconds. In the case of large monitoring data fluctuations, the value of ECS basic monitoring data is smaller than that of agent-collected data.

-   Different monitoring perspectives

    The network traffic data collected by monitoring ECS basic metrics is used for billing. It does not include the traffic between ECS and SLB because such traffic is not billed. However, the network traffic data collected through the CloudMonitor agent records the actual network traffic of each NIC. Therefore, the network traffic data collected through the agent is greater than that collected by monitoring ECS basic metrics \(that is, the agent-collected data value is greater than the actually purchased bandwidth or traffic quota\).


## Agent-collected metrics {#section_an5_yjd_xdb .section}

-   CPU metrics

    You can refer to the Linux top command to understand the meaning of the metrics listed in the following table.

    |Metric|Definition|Unit|Description|
    |:-----|:---------|:---|:----------|
    |Host.cpu.idle|The percentage of CPU currently not utilized|%|The percentage of CPU currently in the idle state.|
    |Host.cpu.system|The percentage of CPU currently occupied by the kernel space|%|Measures the CPU occupied by system context switchover. A great value indicates that many processes or threads are running on the server.|
    |Host.cpu.user|The percentage of CPU currently occupied by user processes|%|Measures the CPU occupied by user processes.|
    |Host.cpu.iowait|The percentage of CPU currently waiting for I/O operations|%|A high value indicates frequent I/O operations.|
    |Host.cpu.other|The percentage of CPU occupied by other operations|%|Calculation method: CPU usage of Nice + CPU usage of SoftIrq + CPU usage of Irq + CPU usage of Stolen.|
    |Host.cpu.totalUsed|The percentage of CPU currently occupied|%|The sum of the preceding CPU consumption. It is usually used for alarm purposes.|

-   Memory metrics

    You can refer to the free command to understand the meaning of the metrics listed in the following table.

    |Metric|Definition|Unit|Description|
    |:-----|:---------|:---|:----------|
    |Host.mem.total|Total memory|Byte|The total memory of the server.|
    |Host.mem.used|The amount of memory in use|Byte|Calculation method: the memory used by user programs + buffers + cached. "buffers" is the memory space occupied by the buffer. "cached" is the memory space occupied by system cache.|
    |Host.mem.actualused|The memory actually used by the user|Byte|     -   Calculation method 1: the memory in use - buffers - cached.
    -   Calculation method 2: total memory - available memory. CentOS 7.2, Ubuntu 16.04, and later versions use the new Linux kernel, which is more accurate in memory estimation. For the specific meaning of the column of available, refer to [Commit](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=34e431b0ae398fc54ea69ff85ec700722c9da773).
 |
    |Host.mem.free|The amount of the memory not in use|Byte|Calculation method: total memory - memory in use.|
    |Host.mem.freeutilization|The percentage of available memory|%|Calculation method: available memory/total memory × 100%.|
    |Host.mem.usedutilization|The memory usage|%|Calculation method: actually used memory/total memory × 100%.|

-   Metrics of average system loads

    You can refer to the Linux TOP command to understand the meaning of the metrics listed in the following table. A higher value of a metric indicates a busier system.

    |Metric|Definition|Unit|
    |:-----|:---------|:---|
    |Host.load1|The average system loads over the past one minute. This metric is not available for Windows operating systems.|None|
    |Host.load5|The average system loads over the past five minutes. This metric is not available for Windows operating systems.|None|
    |Host.load15|The average system loads over the past 15 minutes. This metric is not available for Windows operating systems.|None|

-   Disk metrics

    -   You can refer to the Linux df command to understand the disk usage and inode usage metrics.
    -   You can refer to the Linux iostat command to understand the disk read/write metrics.
    |Metric|Definition|Unit|
    |:-----|:---------|:---|
    |Host.diskusage.used|The space of the disk in use|Byte|
    |Host.disk.utilization|The disk usage|%|
    |Host.diskusage.free|The remaining storage space of the disk|Byte|
    |Host.diskussage.total|The total disk storage|Byte|
    |Host.disk.readbytes|The number of bytes read per second on the disk|Byte/s|
    |Host.disk.writebytes|The number of bytes written per second on the disk|Byte/s|
    |Host.disk.readiops|The number of read requests received by the disk per second|requests/s|
    |Host.disk.writeiops|The number of write requests received by the disk per second|requests/s|

-   File system metrics

    |Metric|Definition|Unit|Description|
    |:-----|:---------|:---|:----------|
    |Host.fs.inode|Inode usage|%|This metric is not available for Windows operating systems. Linux and UNIX systems use inode numbers, instead of file names, to identify files. When inode numbers are used up, new files cannot be created even if the disk space has not been filled up. Therefore, the inode usage must be monitored. The number of inode numbers indicates the number of files. A large number of small files can cause a high inode usage.|

-   Network metrics

    -   You can refer to the Linux iftop command to understand the network related metrics. You can refer to the Linux ss command for the collection of TCP connection data.
    -   The following TCP connection data is collected by default: TCP\_TOTAL \(the total number of connections\), ESTABLISHED \(the number of established connections\), and NON\_ESTABLISHED \(the number of connections not in the established state\). If you want to obtain such data, follow these steps:
        -   Linux

            Change the value of `netstat.tcp.disable` in the configuration file cloudmonitor/config/conf.properties to `false` to collect the data. Then, restart the agent.

        -   Windows

            Change the value of `netstat.tcp.disable` in the configuration file C:\\”Program Files”\\Alibaba\\cloudmonitor\\config to `false` to collect the data. Then, restart the agent.

    |Metric|Definition|Unit|
    |:-----|:---------|:---|
    |Host.netin.rate|The number of bits received by the NIC per second, that is, the upstream bandwidth of the NIC|bit/s|
    |Host.netout.rate|The number of bits sent by the NIC per second, that is, the downstream bandwidth of the NIC|bit/s|
    |Host.netin.packages|The number of packets received by the NIC per second|packets/s|
    |Host.netout.packages|The number of packets sent by the NIC per second|packets/s|
    |Host.netin.errorpackage|The number of incoming error packets detected by the drive|packets/s|
    |Host.netout.errorpackages|The number of outgoing error packets detected by the drive|packets/s|
    |Host.tcpconnection|The number of TCP connections in various states, including LISTEN, SYN\_SENT, ESTABLISHED, SYN\_RECV, FIN\_WAIT1, CLOSE\_WAIT, FIN\_WAIT2, LAST\_ACK, TIME\_WAIT, CLOSING, and CLOSED.|None|

-   Process metrics

    -   For the CPU usage and memory usage of processes, refer to the Linux top command. The CPU usage indicates the consumption of multi-core CPUs.
    -   For details about Host.process.openfile, refer to the Linux lsof command.
    -   For details about Host.process.number, refer to the Linux ps aux |grep 'keyword' command.
    |Metric|Definition|Unit|
    |:-----|:---------|:---|
    |Host.process.cpu|The CPU usage of a process|%|
    |Host.process.memory|The memory usage of a process|%|
    |Host.process.openfile|The number of files opened by the current process|Count|
    |Host.process.number|The number of processes that match the specified keyword|Count|


## ECS basic metrics {#section_gxh_1nd_xdb .section}

If your host is an ECS server, the metrics listed in the following table are monitored automatically after you purchase the ECS instance. You do not need to install the agent. The monitoring frequency is one minute.

|Metric|Definition|Unit|
|:-----|:---------|:---|
|ECS.CPUUtilization|CPU usage|%|
|ECS.InternetInRate|The average rate of inbound Internet traffic|bit/s|
|ECS.IntranetInRate|The average rate of inbound intranet traffic|bit/s|
|ECS.InternetOutRate|The average rate of outbound Internet traffic|bit/s|
|ECS.IntranetOutRate|The average rate of outbound intranet traffic|bit/s|
|ECS.SystemDiskReadbps|The number of bytes read on the system disk per second|Byte/s|
|ECS.SystemDiskWritebps|The number of bytes written on the system disk per second|Byte/s|
|ECS.SystemDiskReadOps|The read times of the system disk per second|packets/s|
|ECS.SystemDiskWriteOps|The write times of the system disk per second|times/s|
|ECS.InternetIn|Internet inbound traffic|Byte|
|ECS.InternetOut|Internet outbound traffic|Byte|
|ECS.IntranetIn|Intranet inbound traffic|Byte|
|ECS.IntranetOut|Intranet outbound traffic|Byte|

