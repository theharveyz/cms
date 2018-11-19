# Preset metric item reference {#reference_f5w_f2z_zdb .reference}

## Note {#section_vtc_sjz_zdb .section}

-   Sum is the sum of values obtained in a statistical period. Take Elastic Compute Service \(ECS\) Internet traffic measurement as an example. The unit is KB/min and the statistical period is 5 minutes. Then the returned result is the total traffic in 5 minutes.
-   OpenAPI supports the query of metric data from the last 31 days.
-   The Dimensions for each parameter is a JSON string, for example, `{"instanceId":"i-23gyb3kkd"}`.

## ECS metric reference {#section_w4r_yjz_zdb .section}

-   Basic metrics

    -   No agent is required for obtaining and querying ECS basic metric data.
    -   The Project is named acs\_ecs\_dashboard, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of an ECS instance.
    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |CPUUtilization|CPU usage|percent|instanceId|Average, Minimum, and Maximum|
    |InternetInRate|Inbound Internet bandwidth|bit/s|instanceId|Average, Minimum, and Maximum|
    |IntranetInRate|Inbound private network bandwidth|bit/s|instanceId|Average, Minimum, and Maximum|
    |InternetOutRate|Outbound Internet bandwidth|bit/s|instanceId|Average, and Minimum, and Maximum|
    |IntranetOutRate|Outbound private network bandwidth|bit/s|instanceId|Average, Minimum, and Maximum|
    |InternetOutRate\_Percent|Outbound Internet bandwidth usage|%|instanceId|Average|
    |DiskReadBPS|Total system disk read BPS|Bps|instanceId|Average, Minimum, and Maximum|
    |DiskWriteBPS|Total system disk write BPS|Bps|instanceId|Average, Minimum, and Maximum|
    |DiskReadIOPS|System disk read IOPS|count/second|instanceId|Average, Minimum, and Maximum|
    |DiskWriteIOPS|System disk write IOPS|count/second|instanceId|Average, Minimum, and Maximum|
    |VPC\_PublicIP\_InternetInRate|VPC - Inbound Internet bandwidth|bit/s|instanceId|Average, Minimum, and Maximum|
    |VPC\_PublicIP\_InternetOutRate|VPC - Outbound Internet bandwidth|bit/s|instanceId|Average, Minimum, and Maximum|
    |VPC\_PublicIP\_InternetOutRate\_Percent|VPC - Outbound Internet bandwidth usage|%|instanceId|Average|


-   Operating system metrics

    The minimum value of period is 15 seconds.

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |cpu\_idle|Host.cpu.idle, percentage of CPU in the idle state|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_system|Host.cpu.system, CPU usage of the current kernel space|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_user|Host.cpu.user, CPU usage of the current user space|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_wait|Host.cpu.iowait, percentage of CPU waiting for I/O operation|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_other|Host.cpu.other, CPU usage of other items. Other types of CPU consumption are calculated using the formula Nice + SoftIrq + Irq + Stolen.|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_total|Host.cpu.total, current total CPU usage|%|instanceId|Average, Minimum, and Maximum|
    |memory\_totalspace|Host.mem.total, total memory|byte|instanceId|Average, Minimum, and Maximum|
    |memory\_usedspace|Host.mem.used, memory in use. The calculation formula is as follows: Memory occupied by user programs + Buffers + Cached. Buffers indicates the memory occupied by the buffer, and Cached indicates the memory occupied by the cache.|byte|instanceId|Average, Minimum, and Maximum|
    |memory\_actualusedspace|Host.mem.actualused, memory occupied by the user. The calculation formula is as follows: Used – Buffers – Cached.|byte|instanceId|Average, Minimum, and Maximum|
    |memory\_freespace|Host.mem.free, available memory|byte|instanceId|Average, Minimum, and Maximum|
    |memory\_freeutilization|Host.mem.freeutilization, percentage of available memory|%|instanceId|Average, Minimum, and Maximum|
    |memory\_usedutilization|Host.mem.usedutilization, memory usage|%|instanceId|Average, Minimum, and Maximum|
    |load\_1m|Host.load1, average system load during the past 1 minute. This metric is not available in Windows operating systems.|N/A|instanceId|Average, Minimum, and Maximum|
    |load\_5m|Host.load5, average system load during the past 5 minutes. This metric is not available in Windows operating systems.|N/A|instanceId|Average, Minimum, and Maximum|
    |load\_15m|Host.load15, average system load during the past 15 minutes. This metric is not available in Windows operating systems.|N/A|instanceId|Average, Minimum, and Maximum|
    |diskusage\_used|Host.diskusage.used, disk space in use|byte|instanceId, device|Average, Minimum, and Maximum|
    |diskusage\_utilization|Host.disk.utilization, disk usage|%|instanceId, device|Average, Minimum, and Maximum|
    |diskusage\_free|Host.diskusage.free, available disk space|byte/s|instanceId, device|Average, Minimum, and Maximum|
    |diskusage\_total|Host.diskussage.total, total disk storage|byte|instanceId, device|Average, Minimum, and Maximum|
    |disk\_readbytes|Host.disk.readbytes, number of bytes read from the disk per second|byte/s|instanceId, device|Average, Minimum, and Maximum|
    |disk\_writebytes|Host.disk.writebytes, number of bytes written to the disk per second|byte/s|instanceId, device|Average, Minimum, and Maximum|
    |disk\_readiops|Host.disk.readiops, number of read requests sent to the disk per second|requests/s|instanceId, device|Average, Minimum, and Maximum|
    |disk\_writeiops|Host.disk.writeiops, number of write requests sent to the disk per second|requests/s|instanceId, device|Average, Minimum, and Maximum|
    |fs\_inodeutilization|Host.fs.inode, inode usage|%|instanceId, device|Average, Minimum, and Maximum|
    |networkin\_rate|Host.netin.rate, number of bits received by the network adapter per second, that is, the uplink bandwidth of the network adapter|bit/s|instanceId, device|Average, Minimum, and Maximum|
    |networkout\_rate|Host.netout.rate, number of bits sent by the network adapter per second, that is, the downlink bandwidth of the network adapter|bit/s|instanceId, device|Average, Minimum, and Maximum|
    |networkin\_packages|Host.netin.packages, number of packages received by the network adapter per second|packages/s|instanceId, device|Average, Minimum, and Maximum|
    |networkout\_packages|Host.netout.packages, number of packages sent by the network adapter per second|packages/s|instanceId, device|Average, Minimum, and Maximum|
    |networkin\_errorpackages|Host.netin.errorpackage, number of incoming error packages detected by the drive|packages/s|instanceId, device|Average, Minimum, and Maximum|
    |networkout\_errorpackages|Host.netout.errorpackages, number of outgoing error packages detected by the drive|packages/s|instanceId, device|Average, Minimum, and Maximum|
    |net\_tcpconnection|Host.tcpconnection, number of TCP connections in various states, including, LISTEN, SYN\_SENT, ESTABLISHED, SYN\_RECV, FIN\_WAIT1, CLOSE\_WAIT, FIN\_WAIT2, LAST\_ACK, TIME\_WAIT, CLOSING, and CLOSED|connections|instanceId, state|Average, Minimum, and Maximum|


## ApsaraDB for RDS metric reference {#section_ukj_mkz_zdb .section}

-   The Project is named acs\_rds\_dashboard, the default sampling period is 300 seconds, and the value of Period is 300 or an integer multiple of 300.
-   The minimum sampling period is 60 seconds if 1-minute monitoring frequency is enabled on the RDS console.
-   The instanceId value for Dimensions is the instanceId of an RDS instance.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|CpuUsage|CPU usage|percent|instanceId|Average, Minimum, and Maximum|
|DiskUsage|Disk usage|percent|instanceId|Average, Minimum, and Maximum|
|IOPSUsage|IOPS usage|percent|instanceId|Average, Minimum, and Maximum|
|ConnectionUsage|Connection usage|percent|instanceId|Average, Minimum, and Maximum|
|DataDelay|Read-only instance latency|seconds|instanceId|Average, Minimum, and Maximum|
|MemoryUsage|Memory usage|percent|instanceId|Average, Minimum, and Maximum|
|MySQL\_NetworkInNew|MySQL - inbound network traffic per second|bit/s|instanceId|Average, Minimum, and Maximum|
|MySQL\_NetworkOutNew|MySQL - outbound network traffic per second|bit/s|instanceId|Average, Minimum, and Maximum|
|MySQL\_ActiveSessions|MySQL - active sessions|count|instanceId|Average, Minimum, and Maximum|
|SQLServer\_NetworkInNew|SQLServer - inbound network traffic per second|bit/s|instanceId|Average, Minimum, and Maximum|
|SQLServer\_NetworkOutNew|SQLServer - outbound network traffic per second|bit/s|instanceId|Average, Minimum, and Maximum|

## SLB metric reference {#section_z3w_xkz_zdb .section}

-   The Project is named acs\_slb\_dashboard, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of a Server Load Balancer \(SLB\) instance.
-   The port value for Dimensions is the port number of an SLB instance.
-   The vip value for Dimensions is the endpoint of an SLB instance.

-   Layer-4 protocol metrics

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |HeathyServerCount|Number of healthy backend ECS instances|count|instanceId|Average, Minimum, and Maximum|
    |UnhealthyServerCount|Number of faulty backend ECS instances|count|instanceId|Average, Minimum, and Maximum|
    |PacketTX|Number of outgoing packets per second on the port|count/second|instanceId, port, vip|Average, Minimum, and Maximum|
    |PacketRX|Number of incoming packets per second on the port|count/second|instanceId, port, vip|Average, Minimum, and Maximum|
    |TrafficRXNew|Inbound data volume per second on the port|bit/s|instanceId, port, vip|Average, Minimum, and Maximum|
    |TrafficTXNew|Outbound data volume per second on the port|bit/s|instanceId, port, vip|Average, Minimum, and Maximum|
    |ActiveConnection|Number of active connections on the port, that is, the number of connections that clients set up to access SLB|count|instanceId, port, vip|Average, Minimum, and Maximum|
    |InactiveConnection|Number of inactive connections on the port, that is, the number of connections that are idle after access to SLB|count|instanceId, port, vip|Average, Minimum, and Maximum|
    |NewConnection|Current number of new connections on the port|count|instanceId, port, vip|Average, Minimum, and Maximum|
    |MaxConnection|Number of concurrent connections on the port|count|instanceId, port, vip|Average, Minimum, and Maximum|
    |DropConnection|Number of dropped connections per second during monitoring|count/second|instanceId, port, vip|Average, Minimum, and Maximum|
    |DropPacketRX|Number of dropped incoming packets per second during monitoring|count/second|instanceId, port, vip|Average, Minimum, and Maximum|
    |DropPacketTX|Number of dropped outgoing packets per second during monitoring|count/second|instanceId, port, vip|Average, Minimum, and Maximum|
    |DropTrafficRX|Number of dropped incoming bits per second during monitoring|bit/s|instanceId, port, vip|Average, Minimum, and Maximum|
    |DropTrafficTX|Number of dropped outgoing bits per second during monitoring|bit/s|instanceId, port, vip|Average, Minimum, and Maximum|
    |InstanceActiveConnection|Number of active connections per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropConnection|Number of dropped connections per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropPacketRX|Number of dropped incoming packets per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropPacketTX|Number of dropped outgoing packets per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropTrafficRX|Number of dropped incoming bits per second on the instance|bit/s|instanceId|Average, Minimum, and Maximum|
    |InstanceDropTrafficTX|Number of dropped outgoing bits per second on the instance|bit/s|instanceId|Average, Minimum, and Maximum|
    |InstanceInactiveConnection|Number of inactive connections per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstanceMaxConnection|Maximum number of concurrent connections per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstanceNewConnection|Number of new connections per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstancePacketRX|Number of incoming packets per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstancePacketTX|Number of outgoing packets per second on the instance|count/second|instanceId|Average, Minimum, and Maximum|
    |InstanceTrafficRX|Number of incoming bits per second on the instance|bit/s|instanceId|Average, Minimum, and Maximum|
    |InstanceTrafficTX|Number of outgoing bits per second on the instance|bit/s|instanceId|Average, Minimum, and Maximum|

-   Layer-7 protocol metrics

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |Qps|Layer-7 protocol port QPS|count/second|instanceId, port, vip|Average|
    |Rt|Layer-7 protocol port RT|ms|instanceId, port, vip|Average|
    |StatusCode2xx|Layer-7 protocol port status code 2xx|count/second|instanceId, port, vip|Average|
    |StatusCode3xx|Layer-7 protocol port status code 3xx|count/second|instanceId, port, vip|Average|
    |StatusCode4xx|Layer-7 protocol port status code 4xx|count/second|instanceId, port, vip|Average|
    |StatusCode5xx|Layer-7 protocol port status code 5xx|count/second|instanceId, port, vip|Average|
    |StatusCodeOther|Layer-7 protocol port status code others|count/second|instanceId, port, vip|Average|
    |UpstreamCode4xx|Layer-7 protocol port Upstream status code 4xx|count/second|instanceId, port, vip|Average|
    |UpstreamCode5xx|Layer-7 protocol port Upstream status code 5xx|count/second|instanceId, port, vip|Average|
    |UpstreamRt|Layer-7 protocol port UpstreamRT|ms|instanceId, port, vip|Average|
    |InstanceQps|Layer-7 protocol instance QPS|count/second|instanceId|Average|
    |InstanceRt|Layer-7 protocol instance RT|ms|instanceId|Average|
    |InstanceStatusCode2xx|Layer-7 protocol instance status code 2xx|count/second|instanceId|Average|
    |InstanceStatusCode3xx|Layer-7 protocol instance status code 3xx|count/second|instanceId|Average|
    |InstanceStatusCode4xx|Layer-7 protocol instance status code 4xx|count/second|instanceId|Average|
    |InstanceStatusCode5xx|Layer-7 protocol instance status code 5xx|count/second|instanceId|Average|
    |InstanceStatusCodeOther|Layer-7 protocol instance status code Other|count/second|instanceId|Average|
    |InstanceUpstreamCode4xx|Layer-7 protocol instance Upstream status code 4xx|count/second|instanceId|Average|
    |InstanceUpstreamCode5xx|Layer-7 protocol instance Upstream status code 5xx|count/second|instanceId|Average|
    |InstanceUpstreamRt|Layer-7 protocol instance UpstreamRT|ms|instanceId|Average|


## OSS metric reference {#section_hmw_nlz_zdb .section}

For details, see [OSS metric reference](https://www.alibabacloud.com/help/doc-detail/31879.htm).

## ApsaraDB for Memcache metric reference {#section_bbq_nlz_zdb .section}

-   New version

    -   The Project is named acs\_memcache, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of a Memcache instance.
    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |ConnectionUsage|Connection usage|percent|instanceId|Average, Minimum, and Maximum|
    |UsedConnection|Number of used connections|count|instanceId|Average, Minimum, and Maximum|
    |CpuUsage|CPU usage|percent|instanceId|Average, Minimum, and Maximum|
    |FailedCount|Number of operation failures|count/second|instanceId|Average, Minimum, and Maximum|
    |IntranetIn|Write network bandwidth|byte/s|instanceId|Average, Minimum, and Maximum|
    |IntranetInRatio|Write bandwidth usage|percent|instanceId|Average, Minimum, and Maximum|
    |IntranetOut|Read network bandwidth|byte/s|instanceId|Average, Minimum, and Maximum|
    |IntranetOutRatio|Read bandwidth usage|percent|instanceId|Average, Minimum, and Maximum|
    |MemoryUsage|Memory usage|percent|instanceId|Average, Minimum, and Maximum|
    |UsedMemory|Used memory|byte|instanceId|Average, Minimum, and Maximum|

-   Old version

    -   The Project is named acs\_ocs, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of an ApsaraDB for Memcache instance.
    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |Evict|Amount of data evicted from the cache per second|Count/Second|instanceId|Average, Minimum, and Maximum|
    |HitRate|Cache hit rate|percent|instanceId|Average, Minimum, and Maximum|
    |IntranetIn|Cache input bandwidth|byte/s|instanceId|Average, Minimum, and Maximum|
    |IntranetOut|Cache output bandwidth|byte|instanceId|Average, Minimum, and Maximum|
    |ItemCount|Number of cache data items|count|instanceId|Average, Minimum, and Maximum|
    |UsedMemCache|Used cache|byte|instanceId|Average, Minimum, and Maximum|
    |UsedQps|Used QPS|count|instanceId|Average, Minimum, and Maximum|


## EIP metric reference {#section_kns_3mz_zdb .section}

-   The Project is named acs\_vpc\_eip, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of an Elastic IP Address \(EIP\) instance.
-   The ip value for Dimensions is the IP address of an EIP instance.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|net\_tx.rate|Outbound bandwidth|bit/s|instanceId|Value|
|net\_rx.rate|Inbound bandwidth|bit/s|instanceId|Value|
|net\_txPkgs.rate|Number of outgoing packets per second|count/s|instanceId|Value|
|net\_rxPkgs.rate|Number of incoming packets per second|count/s|instanceId|Value|
|out\_ratelimit\_drop\_speed|Speed-limit packet loss rate|pps|instanceId|Average|

## ApsaraDB for Redis metric reference {#section_jzf_dnz_zdb .section}

-   The Project is named acs\_kvstore, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of a Redis instance.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|MemoryUsage|Percentage of memory in use|percent|instanceId|Average, Minimum, and Maximum|
|ConnectionUsage|Percentage of used connections|percent|instanceId|Average, Minimum, and Maximum|
|IntranetInRatio|Percentage of bandwidth consumed during write operations|percent|instanceId|Average, Minimum, and Maximum|
|IntranetOutRatio|Percentage of bandwidth consumed during read operations|percent|instanceId|Average, Minimum, and Maximum|
|IntranetIn|Write speed|bit/s|instanceId|Average, Minimum, and Maximum|
|IntranetOut|Read speed|bit/s|instanceId|Average, Minimum, and Maximum|
|FailedCount|Number of failed operations on KVSTORE|count/second|instanceId|Average, Minimum, and Maximum|
|CpuUsage|CPU usage|percent|instanceId|Average, Minimum, and Maximum|
|UsedMemory|Memory in use|byte|instanceId|Average, Minimum, and Maximum|
|UsedConnection|Number of used connections|count|instanceId|Average, Minimum, and Maximum|
|UsedQPS|Number of used QPS|count/second|instanceId|Average, Minimum, and Maximum|

## Message Service metric reference {#section_npl_dsz_zdb .section}

-   The Project is named acs\_mns\_new, the sampling period is 300 seconds, and the value of Period is 300 or an integer multiple of 300.
-   The region value for Dimensions is the region where the queue is located.
-   The queue for Dimensions is the name of the queue.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|ActiveMessages|Number of active messages|count|region, queue|Average, Minimum, and Maximum|
|InactiveMessages|Number of inactive messages|count|region, queue|Average, Minimum, and Maximum|
|DelayMessages|Number of delayed messages|count|region, queue|Average, Minimum, and Maximum|

## CDN metric reference {#section_cd5_ysz_zdb .section}

-   The Project is named acs\_cdn, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of a CDN instance.

|Metric|Description|Unit|Dimensions|Statistics|
|------|-----------|----|----------|----------|
|QPS|Queries per second, that is, total access requests in a specific time interval|count|instanceId|Average, Minimum, and Maximum|
|BPS|Peak bandwidth, that is, maximum network traffic per unit time|bit/s|instanceId|Average, Minimum, and Maximum|
|hitRate|Bytes hit rate, that is, the probability that request bytes hit the cache in a specific time interval|percent|instanceId|Average, Minimum, and Maximum|
|code4xx|Percentage of HTTP return code 4xx in a specific time interval|percent|instanceId|Average, Minimum, and Maximum|
|code5xx|Percentage of HTTP return code 5xx in a specific time interval|percent|instanceId|Average, Minimum, and Maximum|
|InternetOut|Downstream traffic|byte|instanceId|Average, Minimum, and Maximum|

## Analytic DB metric reference {#section_n2c_1tz_zdb .section}

-   The Project is named acs\_ads, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|ads.diskSize|Rated disk capacity|MB|instanceId, tableSchema, workerId|Average, Minimum, and Maximum|
|ads.diskUsed|Used disk capacity|MB|instanceId, tableSchema, workerId|Average, Minimum, and Maximum|
|ads.diskUsedPercent|Disk usage|percent|instanceId, tableSchema, workerId|Average, Minimum, and Maximum|

## ApsaraDB for MongoDB metric reference {#section_phh_btz_zdb .section}

-   The Project is named acs\_mongodb, the sampling period is 300 seconds, and the value of Period is 300 or an integer multiple of 300.
-   The role for Dimensions is Primary or Secondary, which indicates a primary or secondary instance.

|Metric|Metric name|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:----------|:---|:---------|:---------|
|CPUUtilization|CPU usage|CPU usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|MemoryUtilization|Memory usage|Memory usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|DiskUtilization|Disk usage|Disk usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|IOPSUtilization|IOPS usage|IOPS usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|ConnectionUtilization|Connection usage|Percentage of used connections|%|userId, instanceId, role|Average, Minimum, and Maximum|
|QPS|Average SQL queries per second|Average number of SQL queries per second on the MongoDB instance|queries|userId, instanceId, role|Average, Minimum, and Maximum|
|ConnectionAmount|Connections in use|Current number of connections that applications have established with the MongoDB instance|connections|userId, instanceId, role|Average, Minimum, and Maximum|
|InstanceDiskAmount|Disk space used by an instance|Disk space used by an instance|byte|userId, instanceId, role|Average, Minimum, and Maximum|
|DataDiskAmount|Disk space used by data|Disk space used by data|byte|userId, instanceId, role|Average, Minimum, and Maximum|
|LogDiskAmount|Disk space used by logs|Disk space used by logs|byte|userId, instanceId, role|Average, Minimum, and Maximum|
|IntranetIn|Inbound network traffic|Inbound network traffic of the instance|byte|userId, instanceId, role|Average, Minimum, and Maximum|
|intranet\_out|Outbound network traffic|Outbound network traffic of the instance|byte|userId, instanceId, role|Average, Minimum, and Maximum|
|NumberRequests|Request count|Total number of requests sent to the server|requests|userId, instanceId, role|Average, Minimum, and Maximum|
|OpInsert|Insert operations|Total number of insert commands received since the last time MongoDB was started|times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpQuery|Query operations|Total number of query commands received since the last time MongoDB was started|times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpUpdate|Update operations|Total number of update commands received since the last time MongoDB was started|times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpDelete|Delete operations|Total number of delete operations performed since the last time MongoDB was started|times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpGetmore|Getmore operations|Total number of getmore operations performed since the last time MongoDB was started|times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpCommand|Command operations|Total number of commands sent to the database since the last time MongoDB was started|times|userId, instanceId, role|Average, Minimum, and Maximum|

## Express Connect metric reference {#section_zp2_2tz_zdb .section}

-   The Project is named acs\_express\_connect,the sampling period is 60 seconds, and the value of Period 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the interface ID of the Express Connect router.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|IntranetRX|Inbound network traffic|byte|instanceId|
|IntranetTX|Outbound network traffic|byte|instanceId|
|ReceiveBandwidth|Inbound network bandwidth|bit/s|instanceId|
|TransportedBandwidth|Outbound network bandwidth|bit/s|instanceId|
|RouterInterfaceResponseTime|Latency|ms|instanceId|
|RouterInterfaceLossRate|Packet loss rate|%|instanceId|

## Function Compute metric reference {#section_d5t_2tz_zdb .section}

-   The Project is named acs\_fc,the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
-   China East 2: region=cn-shanghai

|Metric|Unit|Dimensions|
|:-----|:---|:---------|
|FunctionAvgDuration|ms|region, serviceName, functionName|
|FunctionBillableInvocations|count|region, serviceName, functionName|
|FunctionBillableInvocationsRate|percent|region, serviceName, functionName|
|FunctionClientErrors|count|region, serviceName, functionName|
|FunctionClientErrorsRate|percent|region, serviceName, functionName|
|FunctionServerErrors|count|region, serviceName, functionName|
|FunctionServerErrorsRate|percent|region, serviceName, functionName|
|FunctionThrottles|count|region, serviceName, functionName|
|FunctionThrottlesRate|percent|region, serviceName, functionName|
|FunctionTotalInvocations|count|region, serviceName, functionName|
|RegionBillableInvocations|count|region|
|RegionBillableInvocationsRate|percent|region|
|RegionClientErrors|count|region|
|RegionClientErrorsRate|percent|region|
|RegionServerErrors|count|region|
|RegionServerErrorsRate|percent|region|
|RegionThrottles|count|region|
|RegionThrottlesRate|percent|region|
|RegionTotalInvocations|count|region|
|ServiceBillableInvocations|count|region, serviceName|
|ServiceBillableInvocationsRate|percent|region, serviceName|
|ServiceClientErrors|count|region, serviceName|
|ServiceClientErrorsRate|percent|region, serviceName|
|ServiceServerErrors|count|region, serviceName|
|ServiceServerErrorsRate|percent|region, serviceName|
|ServiceThrottles|count|region, serviceName|
|ServiceThrottlesRate|percent|region, serviceName|
|ServiceTotalInvocations|count|region, serviceName|

## NAT Gateway metric reference {#section_ck3_ftz_zdb .section}

-   The Project is named acs\_nat\_gateway,the sampling period is 60 seconds, and the value of Period 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|Remarks|
|:-----|:----------|:---|:---------|:------|
|SnatConnection|SNAT connections|count/min|instanceId|The instanceId indicates the instance ID of the NAT Gateway.|
|net\_rx.rate|Inbound bandwidth|bit/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.rate|Outbound network bandwidth|bit/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_rx.Pkgs|Inbound network packages|packages/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.Pkgs|Outbound network packages|packages/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.ratePercent|Outbound network bandwidth usage|%|instanceId|The instanceId indicates the bandwidth package ID.|

## Log Service metric reference {#section_n4k_ttz_zdb .section}

-   The Project is named acs\_sls\_dashboard,the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|LogInflow|Write traffic|byte|project, logstore|
|NetFlow|Raw data size|byte|project, logstore|
|SumQPS|Total QPS|count|project, logstore|
|LogMethodQPS|Operation times|count|project, logstore|
|LogCodeQPS|Service status|count|project, logstore|
|SuccessdByte|Traffic successfully parsed by client|byte|project, logstore|
|SuccessdLines|Lines successfully parsed by client|lines|project, logstore|
|FailedLines|Lines fail to be parsed by client|lines|project, logstore|
|AlarmPV|Client errors|count|project, logstore|
|AlarmUV|Client error machines|count|project, logstore|
|AlarmIPCount|Error IP statistics|count|project, logstore|
|InflowLine|Write lines|lines|project, logstore|
|LogOutflow|Read traffic|byte|project, logstore|
|ConsumerGroupFallBehind|Consumer falling behind duration|second|project, logstore|

## Container Service metric reference {#section_jwc_5tz_zdb .section}

-   The Project is named acs\_containerservice\_dashboard,the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|CpuUtilization|CPU usage|%|clusterId, serviceId, instanceId|
|InternetInRate|Inbound network bandwidth|byte/s|clusterId, serviceId, instanceId|
|InternetOutRate|Outbound network bandwidth|byte/s|clusterId, serviceId, instanceId|
|MemoryAmount|Memory amount|byte|clusterId, serviceId, instanceId|
|MemoryUtilization|Memory usage|%|clusterId, serviceId, instanceId|
|IOReadRate|Disk I/O read rate|byte/s|clusterId, serviceId, instanceId|
|IOWriteRate|Disk I/O write rate|byte/s|clusterId, serviceId, instanceId|
|GPUMemoryUsed|Used GPU memory|byte|clusterId, serviceId, instanceId|
|GPUTemperature|GPU temperature|℃|clusterId, serviceId, instanceId|
|GPUUsed|GPU usage|%|clusterId, serviceId, instanceId|

## VPN Gateway metric reference {#section_f4k_ztz_zdb .section}

-   The Project is named acs\_vpn, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.

|Metric|Description|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|net\_rx.rate|Inbound network bandwidth|bit/s|instanceId|
|net\_tx.rate|Outbound network bandwidth|bit/s|instanceId|
|net\_rx.Pkgs|Number of inbound network packages per second|package/s|instanceId|
|net\_tx.Pkgs|Number of outbound network packages per second|package/s|instanceId|

## Shared bandwidth metric reference {#section_rvz_ztz_zdb .section}

-   The Project is named acs\_bandwidth\_package, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.

|Metric|Description|Unit|Dimensions|Remarks|
|:-----|:----------|:---|:---------|:------|
|net\_rx.rate|Inbound network bandwidth|bit/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.rate|Outbound network bandwidth|bit/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_rx.Pkgs|Inbound network packages|package/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.Pkgs|Outbound network packages|package/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.ratePercent|Outbound network bandwidth usage|%|instanceId|The instanceId indicates the ID of the shared bandwidth.|

## Cloud Enterprise Network metric reference {#section_jpm_15z_zdb .section}

-   The Project is named acs\_cen, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.

|Metric|Description|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|InternetOutRatePercentByConnectionArea|Outbound bandwidth percentage by area|%|cenId, geographicSpanId|
|InternetOutRatePercentByConnectionRegion|Outbound bandwidth percentage by region|%|cenId, geographicSpanId, localRegionId, oppositeRegionId|
|InternetOutRateByConnectionArea|Outbound bandwidth by area|bit/s|cenId, geographicSpanId|
|InternetOutRateByConnectionRegion|Outbound bandwidth by region|bit/s|cenId, geographicSpanId, localRegionId, oppositeRegionId|
|LatencyByConnectionRegion|Region latency|ms|src\_region\_id, dst\_region\_id|
|VBRHealthyCheckLatency|VBR latency|ms|cenId, vbrInstanceId|
|VBRHealthyCheckLossRate|VBR packet loss rate|%|cenId, vbrInstanceId|
|VBRInternetOutRate|VBR outbound bandwidth|bit/s|cenId, vbrInstanceId|
|VBRInternetInRate|VBR inbound bandwidth|bit/s|cenId, vbrInstanceId|

## Edge Node Service metric reference {#section_ryf_4pp_1fb .section}

-   The project is named acs\_ens, the sampling period is 300 seconds, and the value of Period is 300 or an integer multiple of 300.
-   nodeId indicates the city and the operator. For example, cn-kunming-telecom indicates Kunming Telecom, cn-wuhan-cmcc indicates Wuhan Mobile, and cn-wuhan-cucc indicates Wuhan Unicom.
-   instanceId indicates the instance ID.

|Metric|Description|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|instance\_internetin\_rate|Instance-dimension uplink network bandwidth|bit/s|nodeId, instanceId|
|instance\_internetout\_rate|Instance-dimension downlink network bandwidth|bit/s|nodeId, instanceId|
|node\_internetin\_rate|Node-dimension uplink network bandwidth|bit/s|nodeId|
|node\_internetout\_rate|Node-dimension downlink network bandwidth|bit/s|nodeId|
|user\_internetin\_rate|User-dimension uplink network bandwidth|bit/s|Null|
|user\_internetout\_rate|User-dimension downlink network bandwidth|bit/s|Null|

## Open Search metric reference {#section_shg_kvz_cfb .section}

-   The project is named acs\_opensearch.. For details about the sampling period, see the following table.
-   The regionId value for Dimensions can be queried through [DescribeRegions](https://www.alibabacloud.com/help/doc-detail/25609.htm).

|Metric|Description|Unit|Dimensions|Minimum monitoring granularity|
|:-----|:----------|:---|:---------|:-----------------------------|
|DocSizebyApp|Storage capacity|byte|regionId, appName, appId|10 minutes|
|DocSizeRatiobyApp|Storage capacity usage|%|regionId, appName, appId|10 minutes|
|DocCountbyApp|Documents|count|regionId, appName, appId|10 minutes|
|QPSbyApp|Query QPS|count/second|regionId, appName, appId|20 seconds|
|LossQPSbyApp|Query limit QPS|count/second|regionId, appName, appId|20 seconds|
|LatencybyApp|Time consumed for query|ms|regionId, appName, appId|20 seconds|
|ComputeResourcebyApp|Compute resource|LCU|regionId, appName, appId|20 seconds|
|ComputeResourceRatiobyApp|Compute resource usage|%|regionId, appName, appId|20 seconds|
|ComputeCostbyApp|Single query compute cost|LCU|regionId, appName, appId|20 seconds|

## Secure Acceleration metric reference {#section_ibv_2r4_kfb .section}

-   The project is named acs\_scdn, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the domain name of Secure Acceleration.

|Metric|Description|Unit|Dimensions|Statistics|
|------|-----------|----|----------|----------|
|BPS|Network bandwidth|bit/s|instanceId|Average, Minimum, and Maximum|
|code4xx|Proportion of the return code 4xx|%|instanceId|Average, Minimum, and Maximum|
|code5xx|Proportion of the return code 5xx|%|instanceId|Average, Minimum, and Maximum|
|hitRate|Hit rate|%|instanceId|Average, Minimum, and Maximum|
|QPS|Visits per second|count|instanceId|Average, Minimum, and Maximum|

## Global Acceleration metric reference {#section_hgh_bt4_kfb .section}

-   The project is named acs\_scdn, the sampling period is 60 seconds, and the value of Period is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the domain name of Global Acceleration.

|Metric|Description|Unit|Dimensions|Statistics|
|------|-----------|----|----------|----------|
|BPS|Network bandwidth|bit/s|instanceId|Average, Minimum, and Maximum|
|code4xx|Proportion of the return code 4xx|%|instanceId|Average, Minimum, and Maximum|
|code5xx|Proportion of the return code 5xx|%|instanceId|Average, Minimum, and Maximum|
|hitRate|Hit rate|%|instanceId|Average, Minimum, and Maximum|
|QPS|Visits per second|count|instanceId|Average, Minimum, and Maximum|

