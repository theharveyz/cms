# Preset metric item reference {#reference_f5w_f2z_zdb .reference}

## Note {#section_vtc_sjz_zdb .section}

-   "Sum" is the sum of values obtained in a statistical period. Take ECS Internet traffic measurement as an example. The unit is KB/min and the statistical period is 5 minutes. Then the returned result is the total traffic in 5 minutes.
-   OpenAPI supports the query of metric data from the last 31 days.
-   The Dimensions for each parameter is a JSON string, for example, `{"instanceId":"i-23gyb3kkd"}`.

## ECS metric reference {#section_w4r_yjz_zdb .section}

-   Basic metrics

    -   No agent is required for obtaining and querying ECS basic metric data.
    -   The Project is named acs\_ecs\_dashboard, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of the ECS instance.
    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |CPUUtilization|CPU usage|Percent|instanceId|Average, Minimum, and Maximum|
    |InternetInRate|Inbound public network bandwidth|bits/s|instanceId|Average, Minimum, and Maximum|
    |IntranetInRate|Inbound private network bandwidth|bits/s|instanceId|Average, Minimum, and Maximum|
    |InternetOutRate|Outbound public network bandwidth|bits/s|instanceId|Average, Minimum, and Maximum|
    |IntranetOutRate|Outbound private network bandwidth|bits/s|instanceId|Average, Minimum, and Maximum|
    |InternetOutRate\_Percent|Outbound public network bandwidth usage|%|instanceId|Average |
    |DiskReadBPS|Total system disk read BPS|Bps|instanceId|Average, Minimum, and Maximum|
    |DiskWriteBPS|Total system disk write BPS|Bps|instanceId|Average, Minimum, and Maximum|
    |DiskReadIOPS|System disk read IOPS|Count/Second|instanceId|Average, Minimum, and Maximum|
    |DiskWriteIOPS|System disk write IOPS|Count/Second|instanceId|Average, Minimum, and Maximum|
    |VPC\_PublicIP\_InternetInRate|VPC - Inbound public network bandwidth|bits/s|instanceId|Average, Minimum, and Maximum|
    |VPC\_PublicIP\_InternetOutRate|VPC - Outbound public network bandwidth|bits/s|instanceId|Average, Minimum, and Maximum|
    |VPC\_PublicIP\_InternetOutRate\_Percent|VPC - Outbound public network bandwidth usage|%|instanceId|Average |


-   Operating system metrics

    The minimum period is 15 seconds.

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |cpu\_idle|Host.cpu.idle, percentage of CPU in the idle state |%|instanceId|Average, Minimum, and Maximum|
    |cpu\_system|Host.cpu.system, CPU usage of the current kernel space|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_user|Host.cpu.user, CPU usage of the current user space|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_wait|Host.cpu.iowait, percentage of CPU waiting for I/O operation|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_other|Host.cpu.other, CPU usage of other items. Other types of CPU consumption are calculated using the formula Nice + SoftIrq + Irq + Stolen.|%|instanceId|Average, Minimum, and Maximum|
    |cpu\_total|Host.cpu.total, current total CPU usage|%|instanceId|Average, Minimum, and Maximum|
    |memory\_totalspace|Host.mem.total, total memory|bytes|instanceId|Average, Minimum, and Maximum|
    |memory\_usedspace|Host.mem.used, memory in use. The calculation formula is as follows: Memory occupied by user programs + Buffers + Cached. Buffers indicates the memory occupied by the buffer, and Cached indicates the memory occupied by the cache.|bytes|instanceId|Average, Minimum, and Maximum|
    |memory\_actualusedspace|Host.mem.actualused, memory occupied by the user. The calculation formula is as follows: Used – Buffers – Cached.|bytes|instanceId|Average, Minimum, and Maximum|
    |memory\_freespace|Host.mem.free, available memory|bytes|instanceId|Average, Minimum, and Maximum|
    |memory\_freeutilization|Host.mem.freeutilization, percentage of available memory|%|instanceId|Average, Minimum, and Maximum|
    |memory\_usedutilization|Host.mem.usedutilization, memory usage|%|instanceId|Average, Minimum, and Maximum|
    |load\_1m|Host.load1, average system load during the past minute. This metric is not available in Windows.|None|instanceId|Average, Minimum, and Maximum|
    |load\_5m|Host.load5, average system load during the past 5 minutes. This metric is not available in Windows.|None|instanceId|Average, Minimum, and Maximum|
    |load\_15m|Host.load15, average system load during the past 15 minutes. This metric is not available in Windows.|None|instanceId|Average, Minimum, and Maximum|
    |diskusage\_used|Host.diskusage.used, disk space in use|bytes|instanceId, device|Average, Minimum, and Maximum|
    |diskusage\_utilization|Host.disk.utilization, disk usage|%|instanceId, device|Average, Minimum, and Maximum|
    |diskusage\_free|Host.diskusage.free, available disk space|bytes/s|instanceId, device|Average, Minimum, and Maximum|
    |diskusage\_total|Host.diskussage.total, total disk storage|bytes|instanceId, device|Average, Minimum, and Maximum|
    |disk\_readbytes|Host.disk.readbytes, number of bytes read from the disk per second|bytes/s|instanceId, device|Average, Minimum, and Maximum|
    |disk\_writebytes|Host.disk.writebytes, number of bytes written to the disk per second|bytes/s|instanceId, device|Average, Minimum, and Maximum|
    |disk\_readiops|Host.disk.readiops, number of read requests sent to the disk per second|Requests/s|instanceId, device|Average, Minimum, and Maximum|
    |disk\_writeiops|Host.disk.writeiops, number of write requests sent to the disk per second|Requests/s|instanceId, device|Average, Minimum, and Maximum|
    |fs\_inodeutilization|Host.fs.inode, inode usage|%|instanceId, device|Average, Minimum, and Maximum|
    |networkin\_rate|Host.netin.rate, number of bits received by the network adapter per second, that is, the uplink bandwidth of the network adapter|bits/s| instanceId, device|Average, Minimum, and Maximum|
    |networkout\_rate|Host.netout.rate, number of bits sent by the network adapter per second, that is, the downlink bandwidth of the network adapter|bits/s| instanceId, device|Average, Minimum, and Maximum|
    |networkin\_packages|Host.netin.packages, number of packets received by the network adapter per second|Packets/s|instanceId, device|Average, Minimum, and Maximum|
    |networkout\_packages|Host.netout.packages, number of packets sent by the network adapter per second|Packets/s|instanceId, device|Average, Minimum, and Maximum|
    |networkin\_errorpackages|Host.netin.errorpackage, number of incoming error packets detected by the drive|Packets/s|instanceId, device|Average, Minimum, and Maximum|
    |networkout\_errorpackages|Host.netout.errorpackages, number of outgoing error packets detected by the drive|Packets/s|instanceId, device|Average, Minimum, and Maximum|
    |net\_tcpconnection|Host.tcpconnection, number of TCP connections in various states, including LISTEN, SYN\_SENT, ESTABLISHED, SYN\_RECV, FIN\_WAIT1, CLOSE\_WAIT, FIN\_WAIT2, LAST\_ACK, TIME\_WAIT, CLOSING, and CLOSED|Requests|instanceId, state|Average, Minimum, and Maximum|


## ApsaraDB for RDS metric reference {#section_ukj_mkz_zdb .section}

-   The Project is named acs\_rds\_dashboard, the default sampling period is 300s, and the Period value is 300 or an integer multiple of 300.
-   The minimum sampling period is 60s if 1-minute monitoring frequency is enabled on the RDS Console.
-   The instanceId value for Dimensions is the instanceId of the RDS instance.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|CpuUsage|CPU usage|Percent|instanceId, type= CpuUsage|Average, Minimum, and Maximum|
|DiskUsage|Disk usage|Percent|instanceId, type= DiskUsage|Average, Minimum, and Maximum|
|IOPSUsage|IOPS usage|Percent|instanceId, type= IOPSUsage|Average, Minimum, and Maximum|
|ConnectionUsage|Connection usage|Percent|instanceId, type= ConnectionUsage|Average, Minimum, and Maximum|
|DataDelay|Read-only instance latency|Seconds|instanceId, type=DataDelay|Average, Minimum, and Maximum|
|MemoryUsage|Memory usage|Percent|instanceId, type= MemoryUsage|Average, Minimum, and Maximum|
|MySQL\_NetworkInNew|MysqlInbound network traffic per second|bits/s|instanceId|Average, Minimum, and Maximum|
|MySQL\_NetworkOutNew|MysqlOutbound network traffic per second|bits/s|instanceId|Average, Minimum, and Maximum|
|SQLServer\_NetworkInNew|SQLServer - inbound network traffic per second|bits/s|instanceId|Average, Minimum, and Maximum|
|SQLServer\_NetworkOutNew|SQLServer - outbound network traffic per second|bits/s|instanceId|Average, Minimum, and Maximum|

## Server Load Balancer metric reference {#section_z3w_xkz_zdb .section}

-   The Project is named acs\_slb\_dashboard, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of the Server Load Balancer instance.
-   The port value for Dimensions is the Server Load Balancer instance port number.
-   The vip value for Dimensions is the Server Load Balancer instance service address.

-   Layer-4 protocol metrics

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |HeathyServerCount|Number of healthy backend ECS instances|Count|instanceId|Average, Minimum, and Maximum|
    |UnhealthyServerCount|Number of faulty backend ECS instances|Count|instanceId|Average, Minimum, and Maximum|
    |PacketTX|Number of outgoing packets per second on the port|Count/Second|instanceId, port, vip||Average, Minimum, and Maximum|
    |PacketRX|Number of incoming packets per second on the port|Count/Second|instanceId, port, vip||Average, Minimum, and Maximum|
    |TrafficRXNew|Inbound data volume per second on the port|bits/s|instanceId, port, vip||Average, Minimum, and Maximum|
    |TrafficTXNew|Outbound data volume per second on the port|bits/s|instanceId, port, vip||Average, Minimum, and Maximum|
    |ActiveConnection|Number of active connections on the port, that is, the number of connections that clients set up to access Server Load Balancer|Count|instanceId, port, vip||Average, Minimum, and Maximum|
    |InactiveConnection|Number of inactive connections on the port, that is, the number of connections that are idle after access to Server Load Balancer|Count|instanceId, port, vip||Average, Minimum, and Maximum|
    |NewConnection|Current number of new connections on the port|Count|instanceId, port, vip||Average, Minimum, and Maximum|
    |MaxConnection|Number of concurrent connections on the port|Count|instanceId, port, vip||Average, Minimum, and Maximum|
    |DropConnection|Number of dropped connections per second during monitoring|Count/Second|instanceId, port, vip||Average, Minimum, and Maximum|
    |DropPacketRX|Number of dropped incoming packets per second during monitoring|Count/Second|instanceId, port, vip||Average, Minimum, and Maximum|
    |DropPacketTX|Number of dropped outgoing packets per second during monitoring|Count/Second|instanceId, port, vip||Average, Minimum, and Maximum|
    |DropTrafficRX|Number of dropped incoming bits per second during monitoring|bits/s|instanceId, port, vip||Average, Minimum, and Maximum|
    |DropTrafficTX|Number of dropped outgoing bits per second during monitoring|bits/s|instanceId, port, vip||Average, Minimum, and Maximum|
    |InstanceActiveConnection|Number of active connections per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropConnection|Number of dropped connections per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropPacketRX|Number of dropped incoming packets per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropPacketTX|Number of dropped outgoing packets per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstanceDropTrafficRX|Number of dropped incoming bits per second on the instance|bits/s|instanceId|Average, Minimum, and Maximum|
    |InstanceDropTrafficTX|Number of dropped outgoing bits per second on the instance|bits/s|instanceId|Average, Minimum, and Maximum|
    |InstanceInactiveConnection|Number of inactive connections per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstanceMaxConnection|Maximum number of concurrent connections per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstanceNewConnection|Number of new connections per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstancePacketRX|Number of incoming packets per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstancePacketTX|Number of outgoing packets per second on the instance|Count/Second|instanceId|Average, Minimum, and Maximum|
    |InstanceTrafficRX|Number of incoming bits per second on the instance|bits/s|instanceId|Average, Minimum, and Maximum|
    |InstanceTrafficTX|Number of outgoing bits per second on the instance|bits/s|instanceId|Average, Minimum, and Maximum|

-   Layer-7 protocol metrics

    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |Qps|Layer-7 protocol port QPS|Count/Second|instanceId, port, vip|Average|
    |Rt|Layer-7 protocol port RT|ms|instanceId, port, vip|Average|
    |StatusCode2xx|Layer-7 protocol port status code 2XX|Count/Second|instanceId, port, vip|Average|
    |StatusCode3xx|Layer-7 protocol port status code 3XX|Count/Second|instanceId, port, vip|Average|
    |StatusCode4xx|Layer-7 protocol port status code 4XX|Count/Second|instanceId, port, vip|Average|
    |StatusCode5xx|Layer-7 protocol port status code 5XX|Count/Second|instanceId, port, vip|Average|
    |StatusCodeOther|Layer-7 protocol port status code others|Count/Second|instanceId, port, vip|Average|
    |UpstreamCode4xx|Layer-7 protocol port Upstream status code 4xx|Count/Second|instanceId, port, vip|Average|
    |UpstreamCode5xx|Layer-7 protocol port Upstream status code 5xx|Count/Second|instanceId, port, vip|Average|
    |UpstreamRt|Layer-7 protocol port UpstreamRT|ms|instanceId, port, vip|Average|
    |InstanceQps|Layer-7 protocol instance QPS|Count/Second|instanceId|Average |
    |InstanceRt|Layer-7 protocol instance RT|ms|instanceId|Average |
    |InstanceStatusCode2xx|Layer-7 protocol instance status code 2XX|Count/Second|instanceId|Average |
    |InstanceStatusCode3xx|Layer-7 protocol instance status code 3XX|Count/Second|instanceId|Average |
    |InstanceStatusCode4xx|Layer-7 protocol instance status code 4XX|Count/Second|instanceId|Average |
    |InstanceStatusCode5xx|Layer-7 protocol instance status code 5XX|Count/Second|instanceId|Average |
    |InstanceStatusCodeOther|Layer-7 protocol instance status code Other|Count/Second|instanceId|Average |
    |InstanceUpstreamCode4xx|Layer-7 protocol instance Upstream status code 4XX|Count/Second|instanceId|Average |
    |InstanceUpstreamCode5xx|Layer-7 protocol instance Upstream status code 5XX|Count/Second|instanceId|Average |
    |InstanceUpstreamRt|Layer-7 protocol instance UpstreamRT|ms|instanceId|Average |


## OSS metric reference {#section_hmw_nlz_zdb .section}

See [OSS metric reference](https://help.aliyun.com/document_detail/31879.html).

## ApsaraDB for Memcache {#section_bbq_nlz_zdb .section}

-   New version

    -   The Project is named acs\_memcache, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of the Memcache instance.
    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |ConnectionUsage|Connection usage|Requests|instanceId|Average, Minimum, and Maximum|
    |UsedConnection|Number of used connections|Count|instanceId|Average, Minimum, and Maximum|
    |CpuUsage|CPU usage|Percent|instanceId|Average, Minimum, and Maximum|
    |FailedCount|Number of operation failures|Count/Second|instanceId|Average, Minimum, and Maximum|
    |IntranetIn|Write network bandwidth|Bytes/s|instanceId|Average, Minimum, and Maximum|
    |IntranetInRatio|Write bandwidth usage|Percent|instanceId|Average, Minimum, and Maximum|
    |IntranetOut|Read network bandwidth|Bytes/s|instanceId|Average, Minimum, and Maximum|
    |IntranetOutRatio|Read bandwidth usage|Percent|instanceId|Average, Minimum, and Maximum|
    |MemoryUsage|Memory usage|Percent|instanceId|Average, Minimum, and Maximum|
    |UsedMemory|Used memory |Bytes|instanceId|Average, Minimum, and Maximum|

-   Old version

    -   The Project is named acs\_ocs, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
    -   The instanceId value for Dimensions is the instanceId of the ApsaraDB for Memcache instance.
    |Metric|Description|Unit|Dimensions|Statistics|
    |:-----|:----------|:---|:---------|:---------|
    |Evict|Amount of data evicted from the cache per second|Count/Second|instanceId|Average, Minimum, and Maximum|
    |HitRate|Cache hit rate|Percent|instanceId|Average, Minimum, and Maximum|
    |IntranetIn|Cache input bandwidth|Bytes/s|instanceId|Average, Minimum, and Maximum|
    |intranet\_out|Cache output bandwidth|Bytes|instanceId|Average, Minimum, and Maximum|
    |ItemCount|Number of cache data items|Count|instanceId|Average, Minimum, and Maximum|
    |UsedMemCache|Used cache|Bytes|instanceId|Average, Minimum, and Maximum|
    |UsedQps|Used QPS|Count|instanceId|Average, Minimum, and Maximum|


## EIP metric reference {#section_kns_3mz_zdb .section}

-   The Project is named acs\_vpc\_eip, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of the EIP instance.
-   The ip value for Dimensions is the IP address of the EIP instance.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|net\_tx.rate|Outbound bandwidth|bits/s|instanceId|Value|
|net\_rx.rate|Inbound bandwidth|bits/s|instanceId|Value|
|net\_txPkgs.rate|Number of outgoing packets per second|Count/s|instanceId|Value|
|net\_rxPkgs.rate|Number of incoming packets per second|Count/s|instanceId|Value|
|out\_ratelimit\_drop\_speed|Speed-limit packet loss rate|pps|instanceId|Average|

## ApsaraDB for Redis {#section_jzf_dnz_zdb .section}

-   The Project is named acs\_kvstore, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of the Redis instance.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|MemoryUsage|Percentage of memory in use|Percent|instanceId|Average, Minimum, and Maximum|
|ConnectionUsage|Percentage of connections in use|Percent|instanceId|Average, Minimum, and Maximum|
|IntranetInRatio|Percentage of bandwidth consumed during write operations|Percent|instanceId|Average, Minimum, and Maximum|
|IntranetOutRatio|Percentage of bandwidth consumed during read operations|Percent|instanceId|Average, Minimum, and Maximum|
|IntranetIn|Write speed|bits/s|instanceId|Average, Minimum, and Maximum|
|IntranetOut|Read speed|bits/s|instanceId|Average, Minimum, and Maximum|
|FailedCount|Number of failed operations on KVSTORE|Count/Second|instanceId|Average, Minimum, and Maximum|
|CpuUsage|CPU usage|Percent|instanceId|Average, Minimum, and Maximum|
|UsedMemory|Memory in use|Bytes|instanceId|Average, Minimum, and Maximum|

## Message Service metric reference {#section_npl_dsz_zdb .section}

-   The Project is named acs\_messageservice\_new, the sampling period is 300s, and the Period value is 300 or an integer multiple of 300.
-   The region value for Dimensions is the region where the queue is located.
-   The queue value for Dimensions is the name of the queue.

|Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|ActiveMessages|Number of active messages|Count|region,queue|Average, Minimum, and Maximum|
|InactiveMessages|Number of inactive messages|Count|region,queue|Average, Minimum, and Maximum|
|DelayMessages|Number of delayed messages|Count|region,queue|Average, Minimum, and Maximum|

## CDN metric reference {#section_cd5_ysz_zdb .section}

-   The Project is named acs\_cdn, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the instanceId of the CDN instance.

|Metric|Description|Unit|Dimensions|Statistics|
|------|-----------|----|----------|----------|
|QPS|Queries per second, that is, total access requests in a specific time interval/Time interval|Count|instanceId|Average, Minimum, and Maximum|
|BPS|Peak bandwidth, that is, maximum network traffic per unit time|bits/s|instanceId|Average, Minimum, and Maximum|
|hitRate|Bytes hit rate, that is, the probability that request bytes hit the cache in a specific time interval|Percent|instanceId|Average, Minimum, and Maximum|
|code4xx|Percentage of HTTP Return Code 4xx in a specific time interval|Percent|instanceId|Average, Minimum, and Maximum|
|code5xx|Percentage of HTTP Return Code 5xx in a specific time interval|Percent|instanceId|Average, Minimum, and Maximum|
|InternetOut|Downstream traffic|Bytes|instanceId|Average, Minimum, and Maximum|

## Analytic DB metric reference {#section_n2c_1tz_zdb .section}

-   The Project is named acs\_ads, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
-   |Metric|Description|Unit|Dimensions|Statistics|
|:-----|:----------|:---|:---------|:---------|
|ads.diskSize|Rated disk capacity|MB|instanceId,tableSchema,workerId|Average, Minimum, and Maximum|
|ads.diskUsed|Used disk capacity|MB|instanceId,tableSchema,workerId|Average, Minimum, and Maximum|
|ads.diskUsedPercent|Disk usage|Percent|instanceId,tableSchema,workerId|Average, Minimum, and Maximum|


## ApsaraDB for MongoDB metric reference {#section_phh_btz_zdb .section}

-   The Project is named acs\_mongodb, the sampling period is 300s, and the Period value is 300 or an integer multiple of 300.
-   The role value for Dimensions is Primary or Secondary, which indicates the primary or secondary instance.

|Metric|Metric name|Description|Unit|Dimensions|Statistics|
|------|-----------|-----------|----|----------|----------|
|CPUUtilization|CPU usage|CPU usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|MemoryUtilization|Memory usage|Memory usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|DiskUtilization|Disk usage|Disk usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|IOPSUtilization|IOPS usage|IOPS usage of the instance|%|userId, instanceId, role|Average, Minimum, and Maximum|
|ConnectionUtilization|Connection usage|Percentage of connections in use|%|userId, instanceId, role|Average, Minimum, and Maximum|
|QPS|Average SQL queries per second|Average number of SQL queries per second on the MongoDB instance|Queries|userId, instanceId, role|Average, Minimum, and Maximum|
|ConnectionAmount|Connections in use|Current number of connections that applications have established with the MongoDB instance|Connections|userId, instanceId, role|Average, Minimum, and Maximum|
|InstanceDiskAmount|Disk space used by instance|Disk space used by instance|Bytes|userId, instanceId, role|Average, Minimum, and Maximum|
|DataDiskAmount|Disk space used by data|Disk space used by data|Bytes|userId, instanceId, role|Average, Minimum, and Maximum|
|LogDiskAmount|Disk space used by logs|Disk space used by logs|Bytes|userId, instanceId, role|Average, Minimum, and Maximum|
|IntranetIn|Inbound network traffic|Inbound network traffic of the instance|Bytes|userId, instanceId, role|Average, Minimum, and Maximum|
|IntranetOut|Outbound network traffic|Outbound network traffic of the instance|Bytes|userId, instanceId, role|Average, Minimum, and Maximum|
|NumberRequests|Request count|Total number of requests sent to the server|Requests|userId, instanceId, role|Average, Minimum, and Maximum|
|OpInsert|Insert operation count|Total number of insert commands received since the last time MongoDB was started|Times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpQuery|Query operation count|Total number of query commands received since the last time MongoDB was started|Times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpUpdate|Update operation count|Total number of update commands received since the last time MongoDB was started|Times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpDelete|Delete operation count|Total number of delete commands executed since the last time MongoDB was started|Times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpGetmore|Getmore operation count|Total number of getmore commands executed since the last time MongoDB was started|Times|userId, instanceId, role|Average, Minimum, and Maximum|
|OpCommand|Command operation count|Total number of commands sent to the database since the last time MongoDB was started|Times|userId, instanceId, role|Average, Minimum, and Maximum|

## Express Connect metric reference {#section_zp2_2tz_zdb .section}

-   The Project is named acs\_express\_connect,the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
-   The instanceId value for Dimensions is the interface ID of the Express Connect router.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|IntranetRX|Inbound network traffic|Bytes|instanceId|
|IntranetTX|Outbound network traffic|Bytes|instanceId|
|ReceiveBandwidth|Inbound network bandwidth|bit/s|instanceId|
|TransportedBandwidth|Outbound network bandwidth|bit/s|instanceId|

## Function Compute metric reference {#section_d5t_2tz_zdb .section}

-   The Project is named acs\_fc,the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.
-   East China 2: region=cn-shanghai

|Metric|Unit|Dimensions|
|:-----|:---|:---------|
|FunctionAvgDuration|ms|region, serviceName, functionName|
|FunctionBillableInvocations|Count|region, serviceName, functionName|
|FunctionBillableInvocationsRate|Percent|region, serviceName, functionName|
|FunctionClientErrors|Count|region, serviceName, functionName|
|FunctionClientErrorsRate|Percent|region, serviceName, functionName|
|FunctionServerErrors|Count|region, serviceName, functionName|
|FunctionServerErrorsRate|Percent|region, serviceName, functionName|
|FunctionThrottles|Count|region, serviceName, functionName|
|FunctionThrottlesRate|Percent|region, serviceName, functionName|
|FunctionTotalInvocations|Count|region, serviceName, functionName|
|RegionBillableInvocations|Count|region|
|RegionBillableInvocationsRate|Percent|region|
|RegionClientErrors|Count|region|
|RegionClientErrorsRate|Percent|region|
|RegionServerErrors|Count|region|
|RegionServerErrorsRate|Percent|region|
|RegionThrottles|Count|region|
|RegionThrottlesRate|Percent|region|
|RegionTotalInvocations|Count|region|
|ServiceBillableInvocations|Count|region, serviceName|
|ServiceBillableInvocationsRate|Percent|region, serviceName|
|ServiceClientErrors|Count|region, serviceName|
|ServiceClientErrorsRate|Percent|region, serviceName|
|ServiceServerErrors|Count|region, serviceName|
|ServiceServerErrorsRate|Percent|region, serviceName|
|ServiceThrottles|Count|region, serviceName|
|ServiceThrottlesRate|Percent|region, serviceName|
|ServiceTotalInvocations|Count|region, serviceName|

## NAT Gateway metric reference {#section_ck3_ftz_zdb .section}

-   The Project is named acs\_nat\_gateway,the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|Remarks|
|:-----|:----------|:---|:---------|:------|
|SnatConnection|SNAT connections|Count/Min|instanceId|The instanceId indicates the instance ID of the NAT gateway.|
|net\_rx.rate|Inbound network bandwidth|bits/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.rate|Outbound network bandwidth|bits/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_rx.Pkgs|Inbound network packages|packages/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.Pkgs|Outbound network packages|packages/s|instanceId|The instanceId indicates the bandwidth package ID.|
|net\_tx.ratePercent|Outbound network bandwidth usage|%|instanceId|The instanceId indicates the bandwidth package ID.|

## Log Service metric reference {#section_n4k_ttz_zdb .section}

-   The Project is named acs\_sls\_dashboard,the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|LogInflow|Write traffic|Bytes|project, logstore|
|NetFlow|Raw data size|Bytes|project, logstore|
|SumQPS|Total QPS|Count|project, logstore|
|LogMethodQPS|Operation times|Count|project, logstore|
|LogCodeQPS|Service status|Count|project, logstore|
|SuccessdByte|Traffic successfully parsed by client|Bytes|project, logstore|
|SuccessdLines|Lines successfully parsed by client|Lines|project, logstore|
|FailedLines|Lines unsuccessfully parsed by client|Lines|project, logstore|
|AlarmPV|Client error count|Count|project, logstore|
|AlarmUV|Client error machine count|Count|project, logstore|
|AlarmIPCount|Error IP statistics|Count|project, logstore|
|InflowLine|Write lines|Lines|project, logstore|
|LogOutflow|Read traffic|Bytes|project, logstore|
|ConsumerGroupFallBehind|Consumer falling behind duration|Second|project, logstore|

## Container Service metric reference {#section_jwc_5tz_zdb .section}

-   The Project is named acs\_containerservice\_dashboard,the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|CpuUtilization|CPU usage|%|clusterId, serviceId, instanceId|
|InternetInRate|Inbound network bandwidth|Bytes/s|clusterId, serviceId, instanceId|
|InternetOutRate|Outbound network bandwidth|Bytes/s|clusterId, serviceId, instanceId|
|MemoryAmount|Memory amount|Bytes|clusterId, serviceId, instanceId|
|MemoryUtilization|Memory usage|%|clusterId, serviceId, instanceId|
|IOReadRate|Disk IO read rate|Bytes/s|clusterId, serviceId, instanceId|
|IOWriteRate|Disk IO write rate|Bytes/s|clusterId, serviceId, instanceId|
|GPUMemoryUsed|GPU memory used|bytes|clusterId, serviceId, instanceId|
|GPUTemperature|GPU temperature|℃|clusterId, serviceId, instanceId|
|GPUUsed|GPU usage |%|clusterId, serviceId, instanceId|

## VPN metric reference {#section_f4k_ztz_zdb .section}

-   The Project is named acs\_vpn, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|net\_rx.rate|Inbound network bandwidth|bits/s|instanceId|
|net\_tx.rate|Outbound network bandwidth|bits/s|instanceId|
|net\_rx.Pkgs|Number of inbound network packages per second|packages/s|instanceId|
|net\_tx.Pkgs|Number of outbound network packages per second|packages/s|instanceId|

## Shared bandwidth metric reference {#section_rvz_ztz_zdb .section}

-   The Project is named acs\_bandwidth\_package, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|Remarks|
|:-----|:----------|:---|:---------|:------|
|net\_rx.rate|Inbound network bandwidth|bits/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.rate|Outbound network bandwidth|bits/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_rx.Pkgs|Inbound network packages|packages/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.Pkgs|Outbound network packages|packages/s|instanceId|The instanceId indicates the ID of the shared bandwidth.|
|net\_tx.ratePercent|Outbound network bandwidth usage|%|instanceId|The instanceId indicates the ID of the shared bandwidth.|

## Cloud Enterprise Network metric reference {#section_jpm_15z_zdb .section}

-   The Project is named acs\_cen, the sampling period is 60s, and the Period value is 60 or an integer multiple of 60.

|Metric|Metric name|Unit|Dimensions|
|:-----|:----------|:---|:---------|
|InternetOutRatePercentByConnectionArea|Outbound bandwidth percentage by area|%|cenId, geographicSpanId|
|InternetOutRatePercentByConnectionRegion|Outbound bandwidth percentage by region|%|cenId, geographicSpanId, localRegionId, oppositeRegionId|
|InternetOutRateByConnectionArea|Outbound bandwidth by area|bits/s|cenId, geographicSpanId|
|InternetOutRateByConnectionRegion|Outbound bandwidth by region|bits/s|cenId, geographicSpanId, localRegionId, oppositeRegionId|
|LatencyByConnectionRegion|Region latency|ms|src\_region\_id, dst\_region\_id|
|VBRHealthyCheckLatency|VBR latency|ms|cenId, vbrInstanceId|
|VBRHealthyCheckLossRate|VBR packet loss rate|%|cenId, vbrInstanceId|
|VBRInternetOutRate|VBR outbound bandwidth|bits/s|cenId, vbrInstanceId|
|VBRInternetInRate|VBR inbound bandwidth|bits/s|cenId, vbrInstanceId|

