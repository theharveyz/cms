# Preset metric reference {#reference_f5w_f2z_zdb .reference}

## Note {#section_vtc_sjz_zdb .section}

-   Sum is the sum of values obtained in a statistical period. For example, for ECS internet traffic measurements, the unit is KB/min and the statistical period is 5 minutes. Therefore, the returned result is the total traffic in 5 minutes.
-   OpenAPI supports the query of metric data from the last 31 days.
-   The dimensions for each parameter is a JSON string. An example format is: `{"instanceId":"i-23gyb3kkd"}`.

## ECS metrics {#section_w4r_yjz_zdb .section}

-   Basic metrics

    -   The CloudMonitor agent is required for obtaining and querying ECS basic metric data.
    -   The Project is named acs\_ecs\_dashboard, the statistical period is 60 seconds \(or 1 minute\), and the value for the period is 60 or an integer that is a multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of an ECS instance.
    |Metric|Description|Unit|Dimension|Statistics|
    |:-----|:----------|:---|:--------|:---------|
    |CPUUtilization|CPU usage|%|InstanceId|Average, minimum, and maximum|
    |InternetInRate|Inbound bandwidth \(Internet\)|bit/s|InstanceId|Average, minimum, and maximum|
    |IntranetInRate|Inbound bandwidth \(intranet\)|bit/s|InstanceId|Average, minimum, and maximum|
    |InternetOutRate|Outbound bandwidth \(Internet\)|bit/s|InstanceId|Average, and minimum, and maximum|
    |IntranetOutRate|Outbound bandwidth \(intranet\)|bit/s|InstanceId|Average, minimum, and maximum|
    |InternetOutRate\_Percent|Outbound bandwidth usage \(Internet\)|%|InstanceId|Average|
    |DiskReadBPS|Total system disk read BPS|byte/s|InstanceId|Average, minimum, and maximum|
    |DiskWriteBPS|Total system disk write BPS|byte/s|InstanceId|Average, minimum, and maximum|
    |DiskReadIOPS|System disk read IOPS|count/s|InstanceId|Average, minimum, and maximum|
    |DiskWriteIOPS|System disk write IOPS|count/s|InstanceId|Average, minimum, and maximum|
    |VPC\_PublicIP\_InternetInRate|VPC - Inbound bandwidth \(Internet\)|bit/s|InstanceId|Average, minimum, and maximum|
    |VPC\_PublicIP\_InternetOutRate|VPC - Outbound bandwidth \(Internet\)|bit/s|InstanceId|Average, minimum, and maximum|
    |VPC\_PublicIP\_InternetOutRate\_Percent|VPC - Outbound bandwidth usage \(Internet\)|%|InstanceId|Average|


-   Operating system metrics

    The minimum value of the Period is 15 seconds.

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |cpu\_idle|The percentage of CPU that is idle|%|InstanceId|Average, minimum, and maximum|
    |cpu\_system|The percentag of CPU occupied by the kernel space|%|InstanceId|Average, minimum, and maximum|
    |cpu\_user|The percentage of CPU occupied by the user space|%|InstanceId|Average, minimum, and maximum|
    |cpu\_wait|The percentage of CPU pending I/O operations|%|InstanceId|Average, minimum, and maximum|
    |cpu\_other|The percentage of CPU usage occypied by other tasks. \(This is calculated by using the formula: Nice + SoftIrq + Irq + Stolen\)|%|InstanceId|Average, minimum, and maximum|
    |cpu\_total|The total percentage of CPU usage occupied|%|InstanceId|Average, minimum, and maximum|
    |memory\_totalspace|Total memory|Byte|InstanceId|Average, minimum, and maximum|
    |memory\_usedspace|Total used memory t. \(This is calculated by using the formula: Memory occupied by user programs + Buffer + Cache\)|Byte|InstanceId|Average, minimum, and maximum|
    |memory\_actualusedspace|Actual memory usage occupied by the user. \(This is calculated by using the formula: Used – Buffer – Cache\)|Byte|InstanceId|Average, minimum, and maximum|
    |memory\_freespace|The amount of available memory|Byte|InstanceId|Average, minimum, and maximum|
    |memory\_freeutilization|The percentage of available memory|%|InstanceId|Average, minimum, and maximum|
    |memory\_usedutilization|Memory usage|%|InstanceId|Average, minimum, and maximum|
    |load\_1m|The average system load during the past 1 minute. This metric is not available for Windows instances.|N/A|InstanceId|Average, minimum, and maximum|
    |load\_5m|The average system load during the past 5 minutes. This metric is not available for Windows instances.|N/A|InstanceId|Average, minimum, and maximum|
    |load\_15m|The average system load during the past 15 minutes. This metric is not available for Windows instances.|N/A|InstanceId|Average, minimum, and maximum|
    |diskusage\_used|The amount of used disk space|Byte|InstanceId, device|Average, minimum, and maximum|
    |diskusage\_utilization|Disk usage percentage|%|InstanceId, device|Average, minimum, and maximum|
    |diskusage\_free|The calculated rate of available disk space|Byte/s|InstanceId, device|Average, minimum, and maximum|
    |diskusage\_total|The total amount of disk storage|Byte|InstanceId, device|Average, minimum, and maximum|
    |disk\_readbytes|The number of bytes read from the disk per second|Byte/s|InstanceId, device|Average, minimum, and maximum|
    |disk\_writebytes|The number of bytes written to the disk per second|Byte/s|InstanceId, device|Average, minimum, and maximum|
    |disk\_readiops|The number of read requests sent to the disk per second|request/s|InstanceId, device|Average, minimum, and maximum|
    |disk\_writeiops|The number of write requests sent to the disk per second|request/s|InstanceId, device|Average, minimum, and maximum|
    |fs\_inodeutilization|The percentage of inode usage|%|InstanceId, device|Average, minimum, and maximum|
    |networkin\_rate|The number of bits received by the network adapter per second \(the upstream bandwidth of the network card\)|bit/s|InstanceId, device|Average, minimum, and maximum|
    |networkout\_rate|The number of bits sent by the network adapter per second \(the downstream bandwidth of the network card\)|bit/s|InstanceId, device|Average, minimum, and maximum|
    |networkin\_packages|The number of packets received by the network adapter per second|packet/s|InstanceId, device|Average, minimum, and maximum|
    |networkout\_packages|The number of packets sent by the network adapter per second|packet/s|InstanceId, device|Average, minimum, and maximum|
    |networkin\_errorpackages|The number of incoming error packets detected by the drive|packet/s|InstanceId, device|Average, minimum, and maximum|
    |networkout\_errorpackages|The number of outgoing error packets detected by the drive|packet/s|InstanceId, device|Average, minimum, and maximum|
    |net\_tcpconnection|The number of TCP connections in several states. including, LISTEN, SYN\_SENT, ESTABLISHED, SYN\_RECV, FIN\_WAIT1, CLOSE\_WAIT, FIN\_WAIT2, LAST\_ACK, TIME\_WAIT, CLOSING, and CLOSED|connection|InstanceId, state|Average, minimum, and maximum|


## ApsaraDB for RDS metrics {#section_ukj_mkz_zdb .section}

-   The Project is named acs\_rds\_dashboard, the default statistical period is 300 seconds \(or 5 minutes\), and the value of the Period is 300 or an integer that is a multiple of 300.
-   If 1-minute minimum monitoring frequency is enabled on the RDS console, the minimum statistical period is 1 minute, or 60 seconds.
-   The instanceId value for Dimensions is the instanceId of an RDS instance.

|Metric|Description|Unit|Dimension|Statistics|
|:-----|:----------|:---|:--------|:---------|
|CpuUsage|The percentage of CPU usage|%|InstanceId|Average, minimum, and maximum|
|DiskUsage|The percentage of disk usage|%|InstanceId|Average, minimum, and maximum|
|IOPSUsage|The percentage of IOPS usage|%|InstanceId|Average, minimum, and maximum|
|ConnectionUsage|The percentage of connection usage|%|InstanceId|Average, minimum, and maximum|
|DataDelay|Read-only instance latency|second|InstanceId|Average, minimum, and maximum|
|MemoryUsage|The percentage of memory usage|%|InstanceId|Average, minimum, and maximum|
|MySQL\_NetworkInNew|The inbound network traffic per second for MySQL|bit/s|InstanceId|Average, minimum, and maximum|
|MySQL\_NetworkOutNew|The outbound network traffic per second for MySQL|bit/s|InstanceId|Average, minimum, and maximum|
|MySQL\_ActiveSessions|Active sessions for MySQL|count|InstanceId|Average, minimum, and maximum|
|SQLServer\_NetworkInNew|Inbound network traffic per second for an SQL server|bit/s|InstanceId|Average, minimum, and maximum|
|SQLServer\_NetworkOutNew|Outbound network traffic per second for an SQL server|bit/s|InstanceId|Average, minimum, and maximum|

## SLB metrics {#section_z3w_xkz_zdb .section}

-   The Project is named acs\_slb\_dashboard, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
-   The instanceId value for Dimensions is the instanceId of an SLB instance.
-   The port value for Dimensions is the port number of an SLB instance.
-   The VIP value for Dimensions is the endpoint of an SLB instance.

-   Layer-4 protocol metrics

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |HeathyServerCount|The number of healthy backend ECS instances|count|InstanceId|Average, minimum, and maximum|
    |UnhealthyServerCount|The number of faulty backend ECS instances|count|InstanceId|Average, minimum, and maximum|
    |PacketTX|The number of outgoing packets per second on a port|count/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |PacketRX|The number of incoming packets per second on a port|count/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |TrafficRXNew|The inbound data volume per second on a port|bit/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |TrafficTXNew|The outbound data volume per second on a port|bit/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |ActiveConnection|The number of active connections on a port \(the number of connections that clients set up to access SLB\)|count|InstanceId, port, and VIP|Average, minimum, and maximum|
    |InactiveConnection|The number of inactive connections on the port \(the number of connections that are idle after access to SLB\)|count|InstanceId, port, and VIP|Average, minimum, and maximum|
    |NewConnection|The number of new connections on the port|count|InstanceId, port, and VIP|Average, minimum, and maximum|
    |MaxConnection|The number of concurrent connections on the port|count|InstanceId, port, and VIP|Average, minimum, and maximum|
    |DropConnection|The number of dropped connections per second|count/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |DropPacketRX|The number of dropped incoming packets per second|count/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |DropPacketTX|The number of dropped outgoing packets per second|count/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |DropTrafficRX|The number of dropped incoming bits per second|bit/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |DropTrafficTX|The number of dropped outgoing bits per second|bit/s|InstanceId, port, and VIP|Average, minimum, and maximum|
    |InstanceActiveConnection|The number of active connections per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstanceDropConnection|Th number of dropped connections per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstanceDropPacketRX|The number of dropped incoming packets per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstanceDropPacketTX|The number of dropped outgoing packets per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstanceDropTrafficRX|The number of dropped incoming bits per second on an instance|bit/s|InstanceId|Average, minimum, and maximum|
    |InstanceDropTrafficTX|The number of dropped outgoing bits per second on an instance|bit/s|InstanceId|Average, minimum, and maximum|
    |InstanceInactiveConnection|The number of inactive connections per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstanceMaxConnection|The maximum concurrent connections per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstanceNewConnection|The number of new connections per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstancePacketRX|The number of incoming packets per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstancePacketTX|The number of outgoing packets per second on an instance|count/s|InstanceId|Average, minimum, and maximum|
    |InstanceTrafficRX|The number of incoming bits per second on an instance|bit/s|InstanceId|Average, minimum, and maximum|
    |InstanceTrafficTX|The number of outgoing bits per second on an instance|bit/s|InstanceId|Average, minimum, and maximum|

-   Layer-7 protocol metrics

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |QPS|Port QPS|count/s|InstanceId, port, and VIP|Average|
    |RT|Port response time|ms|InstanceId, port, and VIP|Average|
    |StatusCode2xx|Port status codes of the format 2xx|count/s|InstanceId, port, and VIP|Average|
    |StatusCode3xx|Port status codes of the format 3xx|count/s|InstanceId, port, and VIP|Average|
    |StatusCode4xx|Port status codes of the format 4xx|count/s|InstanceId, port, and VIP|Average|
    |StatusCode5xx|Port status codes of the format 5xx|count/s|InstanceId, port, and VIP|Average|
    |StatusCodeOther|Port status codes of other formats|count/s|InstanceId, port, and VIP|Average|
    |UpstreamCode4xx|Port upstream status codes of the format 4xx|count/s|InstanceId, port, and VIP|Average|
    |UpstreamCode5xx|Port upstream status codes of the format 5xx|count/s|InstanceId, port, and VIP|Average|
    |UpstreamRt|Port upstream response time|ms|InstanceId, port, and VIP|Average|
    |InstanceQps|Instance QPS|count/s|InstanceId|Average|
    |InstanceRt|Instance response time|ms|InstanceId|Average|
    |InstanceStatusCode2xx|Instance status codes of the format2xx|count/s|InstanceId|Average|
    |InstanceStatusCode3xx|Instance status codes of the format 3xx|count/s|InstanceId|Average|
    |InstanceStatusCode4xx|Instance status codes of the format 4xx|count/s|InstanceId|Average|
    |InstanceStatusCode5xx|Instance status codes of the format 5xx|count/s|InstanceId|Average|
    |InstanceStatusCodeOther|Instance status codes of the format Other|count/s|InstanceId|Average|
    |InstanceUpstreamCode4xx|Instance upstream status codes of the format 4xx|count/s|InstanceId|Average|
    |InstanceUpstreamCode5xx|Instance upstream status codes of the format 5xx|count/s|InstanceId|Average|
    |InstanceUpstreamRt|Instance Upstream response time|ms|InstanceId|Average|


## OSS metrics {#section_hmw_nlz_zdb .section}

For details, see [OSS metric reference](https://www.alibabacloud.com/help/doc-detail/31879.htm).

## ApsaraDB for Memcache metrics {#section_bbq_nlz_zdb .section}

-   New version metrics

    -   The Project is named acs\_memcache, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of a Memcache instance.
    |Metric|Description|Unit|Dimension|Statistics|
    |:-----|:----------|:---|:--------|:---------|
    |ConnectionUsage|The connection usage|%|InstanceId|Average, minimum, and maximum|
    |UsedConnection|The number of used connections|count|InstanceId|Average, minimum, and maximum|
    |CpuUsage|CPU usage|%|InstanceId|Average, minimum, and maximum|
    |FailedCount|The number of operation failures|count/s|InstanceId|Average, minimum, and maximum|
    |IntranetIn|The write network bandwidth|Byte/s|InstanceId|Average, minimum, and maximum|
    |IntranetInRatio|The write bandwidth usage|%|InstanceId|Average, minimum, and maximum|
    |IntranetOut|The read network bandwidth|Byte/s|InstanceId|Average, minimum, and maximum|
    |IntranetOutRatio|The read bandwidth usage|%|InstanceId|Average, minimum, and maximum|
    |MemoryUsage|Memory usage|%|InstanceId|Average, minimum, and maximum|
    |UsedMemory|Used memory|Byte|InstanceId|Average, minimum, and maximum|

-   Old version metrics

    -   The Project is named acs\_ocs, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of an ApsaraDB for Memcache instance.
    |Metric|Description|Unit|Dimension|Statistics|
    |:-----|:----------|:---|:--------|:---------|
    |Evict|The amount of data evicted from the cache per second|count/s|InstanceId|Average, Minimum, and Maximum|
    |HitRate|The cache hit rate|%|InstanceId|Average, minimum, and maximum|
    |IntranetIn|The cache input bandwidth|Byte/s|InstanceId|Average, minimum, and maximum|
    |IntranetOut|The cache output bandwidth|Byte|InstanceId|Average, minimum, and maximum|
    |ItemCount|The number of cache data items|count|InstanceId|Average, minimum, and maximum|
    |UsedMemCache|The used cache|Byte|InstanceId|Average, minimum, and maximum|
    |UsedQps|The used QPS|count|InstanceId|Average, minimum, and maximum|


## EIP metrics {#section_kns_3mz_zdb .section}

-   The Project is named acs\_vpc\_eip, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
-   The instanceId value for Dimensions is the instanceId of an EIP instance.
-   The IP value for Dimensions is the IP address of an EIP instance.

|Metric|Description|Unit|Dimension|Statistics|
|:-----|:----------|:---|:--------|:---------|
|net\_tx.rate|Outbound bandwidth|bit/s|InstanceId|Value|
|net\_rx.rate|Inbound bandwidth|bit/s|InstanceId|Value|
|net\_txPkgs.rate|The number of outgoing packets per second|count/s|InstanceId|Value|
|net\_rxPkgs.rate|The number of incoming packets per second|count/s|InstanceId|Value|
|out\_ratelimit\_drop\_speed|The speed-limit packet loss rate|packet/s|InstanceId|Average|

## ApsaraDB for Redis metrics {#section_jzf_dnz_zdb .section}

-   The Project is named acs\_kvstore, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
-   The instanceId value for Dimensions is the instanceId of a Redis instance.

|Metric|Description|Unit|Dimension|Statistics|
|:-----|:----------|:---|:--------|:---------|
|MemoryUsage|The percentage of memory in use|%|InstanceId|Average, minimum, and maximum|
|ConnectionUsage|The percentage of used connections|%|InstanceId|Average, minimum, and maximum|
|IntranetInRatio|The percentage of bandwidth consumed during write operations|%|InstanceId|Average, minimum, and maximum|
|IntranetOutRatio|The percentage of bandwidth consumed during read operations|%|InstanceId|Average, minimum, and maximum|
|IntranetIn|The write speed|bit/s|InstanceId|Average, minimum, and maximum|
|IntranetOut|The read speed|bit/s|InstanceId|Average, minimum, and maximum|
|FailedCount|The number of failed operations on KVSTORE|count/s|InstanceId|Average, minimum, and maximum|
|CpuUsage|CPU usage|%|InstanceId|Average, minimum, and maximum|
|UsedMemory|Memory in use|Byte|InstanceId|Average, minimum, and maximum|
|UsedConnection|The number of used connections|count|InstanceId|Average, minimum, and maximum|
|UsedQPS|The number of used QPS|count/s|InstanceId|Average, minimum, and maximum|

## Message Service metrics {#section_npl_dsz_zdb .section}

-   The Project is named acs\_mns\_new, the statistical period is 300 seconds \(or 5 minutes\), and the value of the Period is 300 or an integer that is a multiple of 300.
-   The region value for Dimensions is the region where the queue is located.
-   The queue for Dimensions is the name of the queue.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|ActiveMessages|The number of active messages|count|Region andqueue|Average, minimum, and maximum|
|InactiveMessages|The number of inactive messages|count|Region and queue|Average, minimum, and naximum|
|DelayMessages|The number of delayed messages|count|Region and queue|Average, minimum, and maximum|

## CDN metric reference {#section_cd5_ysz_zdb .section}

-   The Project is named acs\_cdn, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
-   The instanceId value for Dimensions is the instanceId of a CDN instance.

|Metric|Description|Unit|Dimension|Statistics|
|------|-----------|----|---------|----------|
|QPS|QPS \(The total access requests in a specific time interval\)|count|InstanceId|Average, minimum, and maximum|
|BPS|Peak bandwidth \(The maximum network traffic per unit time\)|bit/s|InstanceId|Average, minimum, and maximum|
|hitRate|Bytes hit rate \(The probability that request bytes hit the cache\)|%|InstanceId|Average, minimum, and maximum|
|code4xx|The percentage of status codes of the format 4xx|%|InstanceId|Average, minimum, and maximum|
|code5xx|The percentage of status codes of the format 5xx|%|InstanceId|Average, minimum, and maximum|
|InternetOut|Downstream traffic|Byte|InstanceId|Average, minimum, and maximum|

## Analytic DB metrics {#section_n2c_1tz_zdb .section}

-   The Project is named acs\_ads, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|ads.diskSize|Rated disk capacity|MB|InstanceId, tableSchema, and workerId|Average, minimum, and maximum|
|ads.diskUsed|Used disk capacity|MB|InstanceId, tableSchema, and workerId|Average, minimum, and maximum|
|ads.diskUsedPercent|Disk usage|%|InstanceId, tableSchema, and workerId|Average, minimum, and maximum|

## ApsaraDB for MongoDB metrics {#section_phh_btz_zdb .section}

-   The Project is named acs\_mongodb, the statistical period is 300 seconds \(or 5 minutes\), and the value of the Period is 300 or an integer that is a multiple of 300.
-   The role for Dimensions is Primary or Secondary, which indicates a primary or secondary instance.

|Metric|Metric name|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:----------|:---|:---------|:---------|
|CPUUtilization|CPU usage|The CPU usage of an instance|%|UserId, instanceId, and role|Average, minimum, and maximum|
|MemoryUtilization|Memory usage|The memory usage of an instance|%|UserId, instanceId, and role|Average, minimum, and maximum|
|DiskUtilization|Disk usage|The disk usage of an instance|%|UserId, instanceId, and role|Average, minimum, and maximum|
|IOPSUtilization|IOPS usage|The IOPS usage of an instance|%|UserId, instanceId, and role|Average, minimum, and maximum|
|ConnectionUtilization|Connection usage|The percentage of used connections|%|UserId, instanceId, and role|Average, minimum, and maximum|
|QPS|Average SQL queries per second|The average number of SQL QPS on an instance|query|UserId, instanceId, and role|Average, minimum, and maximum|
|ConnectionAmount|Connections in use|The number of connections that applications have established with an instance|connection|UserId, instanceId, and role|Average, minimum, and maximum|
|InstanceDiskAmount|Disk space used by an instance|The disk space used by an instance|Byte|UserId, instanceId, and role|Average, minimum, and maximum|
|DataDiskAmount|Disk space used by data|The disk space used by data|Byte|UserId, instanceId, and role|Average, minimum, and maximum|
|LogDiskAmount|Disk space used by logs|The disk space used by logs|Byte|UserId, instanceId, and role|Average, minimum, and maximum|
|IntranetIn|Inbound network traffic|The inbound network traffic of an instance|Byte|UserId, instanceId, and role|Average, minimum, and maximum|
|intranet\_out|Outbound network traffic|The outbound network traffic of an instance|Byte|UserId, instanceId, and role|Average, minimum, and maximum|
|NumberRequests|Request count|The total number of requests sent to the server|request|UserId, instanceId, and role|Average, minimum, and maximum|
|OpInsert|Insert operations|The total number of insert commands received since the last time MongoDB was started|times|UserId, instanceId, and role|Average, minimum, and maximum|
|OpQuery|Query operations|The total number of query commands received since the last time MongoDB was started|times|UserId, instanceId, and role|Average, minimum, and maximum|
|OpUpdate|Update operations|The total number of update commands received since the last time MongoDB was started|times|UserId, instanceId, and role|Average, minimum, and maximum|
|OpDelete|Delete operations|The total number of delete operations performed since the last time MongoDB was started|times|UserId, instanceId, and role|Average, minimum, and maximum|
|OpGetmore|Getmore operations|The total number of getmore operations performed since the last time MongoDB was started|times|UserId, instanceId, and role|Average, minimum, and maximum|
|OpCommand|Command operations|The total number of commands sent to the database since the last time MongoDB was started|times|UserId, instanceId, and role|Average, minimum, and maximum|

## Express Connect metrics {#section_zp2_2tz_zdb .section}

-   The Project is named acs\_express\_connect,the statistcal period is 60 seconds \(or 1 minute\), and the value of the Period 60 or an integer that is a multiple of 60.
-   The instanceId value for Dimensions is the interface ID of the Express Connect router.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|IntranetRX|Inbound network traffic|Byte|InstanceId|
|IntranetTX|Outbound network traffic|Byte|ItanceId|
|ReceiveBandwidth|Inbound network bandwidth|bit/s|InstanceId|
|TransportedBandwidth|Outbound network bandwidth|bit/s|InstanceId|
|RouterInterfaceResponseTime|Latency|ms|InstanceId|
|RouterInterfaceLossRate|The percentage of the packet loss rate|%|InstanceId|

## Function Compute metrics {#section_d5t_2tz_zdb .section}

-   The Project is named acs\_fc,the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
-   China East 2: region=cn-shanghai

|Metric|Unit|Dimensions|
|:-----|:---|:---------|
|FunctionAvgDuration|ms|Region, serviceName, and functionName|
|FunctionBillableInvocations|count|Region, serviceName, and functionName|
|FunctionBillableInvocationsRate|%|Region, serviceName, and functionName|
|FunctionClientErrors|count|Region, serviceName, and functionName|
|FunctionClientErrorsRate|%|Region, serviceName, and functionName|
|FunctionServerErrors|count|Region, serviceName, and functionName|
|FunctionServerErrorsRate|%|Region, serviceName, and functionName|
|FunctionThrottles|count|Region, serviceName, and functionName|
|FunctionThrottlesRate|%|Region, serviceName, and functionName|
|FunctionTotalInvocations|count|Region, serviceName, and functionName|
|RegionBillableInvocations|count|Region|
|RegionBillableInvocationsRate|%|Region|
|RegionClientErrors|count|Region|
|RegionClientErrorsRate|%|Region|
|RegionServerErrors|count|Region|
|RegionServerErrorsRate|%|Region|
|RegionThrottles|count|Region|
|RegionThrottlesRate|%|Region|
|RegionTotalInvocations|count|Region|
|ServiceBillableInvocations|count|Region and serviceName|
|ServiceBillableInvocationsRate|%|Region and serviceName|
|ServiceClientErrors|count|Region and serviceName|
|ServiceClientErrorsRate|%|Region and serviceName|
|ServiceServerErrors|count|Region and serviceName|
|ServiceServerErrorsRate|%|Region and serviceName|
|ServiceThrottles|count|Region and serviceName|
|ServiceThrottlesRate|%|Region and serviceName|
|ServiceTotalInvocations|count|Region and serviceName|

## NAT Gateway metrics {#section_ck3_ftz_zdb .section}

-   The Project is named acs\_nat\_gateway,the statistical period is 60 seconds \(or 1 minute\), and the value of the Period 60 or an integer that is a multiple of 60.

|Metric|Metric name|Unit|Dimension|Remark|
|:-----|:----------|:---|:--------|:-----|
|SnatConnection|SNAT connections|count/minute|InstanceId|The instanceId indicates the instance ID of the NAT Gateway.|
|net\_rx.rate|Inbound bandwidth|bit/s|InstanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.rate|Outbound network bandwidth|bit/s|InstanceId|The instanceId indicates the bandwidth package ID.|
|net\_rx.Pkgs|Inbound network packets|packet/s|InstanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.Pkgs|Outbound network packets|packet/s|InstanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.ratePercent|Outbound network bandwidth usage|%|InstanceId|The instanceId indicates the bandwidth package ID.|

## Log Service metrics {#section_n4k_ttz_zdb .section}

-   The Project is named acs\_sls\_dashboard,the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|LogInflow|Write traffic|Byte|Project and logstore|
|NetFlow|Raw data size|Byte|Project and logstore|
|SumQPS|Total QPS|count|Project and logstore|
|LogMethodQPS|Operation times|count|Project and logstore|
|LogCodeQPS|Service status|count|Project and logstore|
|SuccessdByte|Traffic successfully parsed by client|Byte|Project and logstore|
|SuccessdLines|Lines successfully parsed by client|line|Project, logstore|
|FailedLines|Lines fail to be parsed by client|line|Project and logstore|
|AlarmPV|Client errors|count|Project and logstore|
|AlarmUV|Client error instances|count|Project and logstore|
|AlarmIPCount|Error IP statistics|count|Project and logstore|
|InflowLine|Write lines|line|Project and logstore|
|LogOutflow|Read traffic|Byte|Project and logstore|
|ConsumerGroupFallBehind|Consumer falling behind duration|second|Project and logstore|

## Container Service metrics {#section_jwc_5tz_zdb .section}

-   The Project is named acs\_containerservice\_dashboard, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|CpuUtilization|CPU usage|%|ClusterId, serviceId, and instanceId|
|InternetInRate|Inbound network bandwidth|Byte/s|ClusterId, serviceId, and instanceId|
|InternetOutRate|Outbound network bandwidth|Byte/s|ClusterId, serviceId, and instanceId|
|MemoryAmount|Memory amount|Byte|ClusterId, serviceId, and instanceId|
|MemoryUtilization|Memory usage|%|ClusterId, serviceId, and instanceId|
|IOReadRate|The disk I/O read rate|Byte/s|ClusterId, serviceId, and instanceId|
|IOWriteRate|The disk I/O write rate|Byte/s|ClusterId, serviceId, and instanceId|
|GPUMemoryUsed|Used GPU memory|Byte|ClusterId, serviceId, and instanceId|
|GPUTemperature|GPU temperature|℃|ClusterId, serviceId, and instanceId|
|GPUUsed|GPU usage|%|ClusterId, serviceId, and instanceId|

## VPN Gateway metrics {#section_f4k_ztz_zdb .section}

-   The Project is named acs\_vpn, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.

|Metric|Description|Unit|Dimension|
|:-----|:----------|:---|:--------|
|net\_rx.rate|Inbound network bandwidth|bit/s|InstanceId|
|net\_tx.rate|Outbound network bandwidth|bit/s|InstanceId|
|net\_rx.Pkgs|The number of inbound network packets per second|packet/s|InstanceId|
|net\_tx.Pkgs|The number of outbound network packets per second|packet/s|InstanceId|

## Shared bandwidth metrics {#section_rvz_ztz_zdb .section}

-   The Project is named acs\_bandwidth\_package, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.

|Metric|Description|Unit|Dimension|Remarks|
|:-----|:----------|:---|:--------|:------|
|net\_rx.rate|Inbound network bandwidth|bit/s|InstanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.rate|Outbound network bandwidth|bit/s|InstanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_rx.Pkgs|Inbound network packets|packet/s|InstanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.Pkgs|Outbound network packets|packet/s|InstanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.ratePercent|Outbound network bandwidth usage|%|InstanceId|The instanceId indicates the ID of the shared bandwidth.|

## Cloud Enterprise Network metrics {#section_jpm_15z_zdb .section}

-   The Project is named acs\_cen, the statiscal period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.

|Metric|Description|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|InternetOutRatePercentByConnectionArea|Outbound bandwidth percentage by area|%|CenId and geographicSpanId|
|InternetOutRatePercentByConnectionRegion|Outbound bandwidth percentage by region|%|CenId, geographicSpanId, localRegionId, and oppositeRegionId|
|InternetOutRateByConnectionArea|Outbound bandwidth by area|bit/s|CenId and geographicSpanId|
|InternetOutRateByConnectionRegion|Outbound bandwidth by region|bit/s|CenId, geographicSpanId, localRegionId, and oppositeRegionId|
|LatencyByConnectionRegion|Region latency|ms|Src\_region\_id and dst\_region\_id|
|VBRHealthyCheckLatency|VBR latency|ms|CenId and vbrInstanceId|
|VBRHealthyCheckLossRate|VBR packet loss rate|%|CenId and vbrInstanceId|
|VBRInternetOutRate|VBR outbound bandwidth|bit/s|CenId and vbrInstanceId|
|VBRInternetInRate|VBR inbound bandwidth|bit/s|CenId and vbrInstanceId|

## Edge Node Service metrics {#section_ryf_4pp_1fb .section}

-   The Project is named acs\_ens, the statistical period is 300 seconds \(or 5 minutes\), and the value of the Period is 300 or an integer that is a multiple of 300.
-   nodeId indicates the city and the operator. For example, cn-kunming-telecom indicates Kunming Telecom, cn-wuhan-cmcc indicates Wuhan Mobile, and cn-wuhan-cucc indicates Wuhan Unicom.
-   instanceId indicates the instance ID.

|Metric|Description|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|instance\_internetin\_rate|The instance downlink network bandwidth|bit/s|NodeId and instanceId|
|instance\_internetout\_rate|The instance uplink network bandwidth|bit/s|NodeId and instanceId|
|node\_internetin\_rate|The node downlink network bandwidth|bit/s|NodeId|
|node\_internetout\_rate|The node uplink network bandwidth|bit/s|NodeId|
|user\_internetin\_rate|The user downlink network bandwidth|bit/s|N/A|
|user\_internetout\_rate|The user uplink network bandwidth|bit/s|N/A|

## Open Search metrics {#section_shg_kvz_cfb .section}

-   The project is named acs\_opensearch. For details about the statistical period, see the following table.
-   The regionId value for Dimensions can be queried through [DescribeRegions](https://www.alibabacloud.com/help/doc-detail/25609.htm).

|Metric|Description|Unit|Dimensions|Minimum monitoring frequency|
|:-----|:----------|:---|:---------|:---------------------------|
|DocSizebyApp|The storage capacity|Byte|RegionId, appName, and appId|10 minutes|
|DocSizeRatiobyApp|The storage capacity usage|%|RegionId, appName, and appId|10 minutes|
|DocCountbyApp|Documents|count|RegionId, appName, and appId|10 minutes|
|QPSbyApp|QPS|count/s|RegionId, appName, and appId|20 seconds|
|LossQPSbyApp|Minimum QPS|count/s|RegionId, appName, and appId|20 seconds|
|LatencybyApp|Time consumed for query|ms|RegionId, appName, and appId|20 seconds|
|ComputeResourcebyApp|Compute resource|LCU|RegionId, appName, and appId|20 seconds|
|ComputeResourceRatiobyApp|Compute resource usage|%|RegionId, appName, and appId|20 seconds|
|ComputeCostbyApp|The cost per single query compute|LCU|RegionId, appName, and appId|20 seconds|

## Secure Acceleration metrics {#section_ibv_2r4_kfb .section}

-   The Project is named acs\_scdn, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
-   The instanceId value for Dimensions is the domain name of Secure Acceleration.

|Metric|Description|Unit|Dimension|Statistics|
|------|-----------|----|---------|----------|
|BPS|The network bandwidth|bit/s|InstanceId|Average, minimum, and maximum|
|code4xx|The percentage of status codes of the format 4xx|%|InstanceId|Average, minimum, and maximum|
|code5xx|The percentage of status codes of the format 5xx|%|InstanceId|Average, minimum, and maximum|
|hitRate|Hit rate|%|InstanceId|Average, minimum, and maximum|
|QPS|Visits per second|count|InstanceId|Average, minimum, and maximum|

## Global Acceleration metrics {#section_hgh_bt4_kfb .section}

-   The Project is named acs\_scdn, the statistical period is 60 seconds \(or 1 minute\), and the value of the Period is 60 or an integer that is a multiple of 60.
-   The instanceId value for Dimensions is the domain name of Global Acceleration.

|Metric|Description|Unit|Dimension|Statistics|
|------|-----------|----|---------|----------|
|BPS|Network bandwidth|bit/s|InstanceId|Average, minimum, and maximum|
|code4xx|The percentage of status codes of the format 4xx|%|InstanceId|Average, minimum, and maximum|
|code5xx|The percentage of status codes of the format 5xx|%|InstanceId|Average, minimum, and maximum|
|hitRate|Hit rate|%|InstanceId|Average, minimum, and maximum|
|QPS|Visits per second|count|InstanceId|Average, minimum, and maximum|

