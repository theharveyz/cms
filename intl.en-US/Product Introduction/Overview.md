# Overview {#concept_n3h_2s4_tdb .concept}

CloudMonitor provides you with an overview of your cloud services, cloud resource usage, alarms, and important events, allowing you to understand the utilization and retention of resources and the alarms for your cloud services in real time.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6123/154511965234450_en-US.png)

## Cloud services overview {#section_sql_ss4_tdb .section}

The cloud services overview provides a summary of the resources that you use, helping you quickly and easily understand the assets you have. The cloud services overview displays the following services:

-   Hosts, including ECS hosts and the non-ECS hosts that are installed with the CloudMonitor agent
-   Server Load Balancer
-   Elastic IP Address
-   ApsaraDB for RDS, MongoDB, Memcache, and Redis
-   OSS
-   CDN
-   Message Service
-   Container Service
-   Log Service
-   StreamCompute
-   Analytic DB
-   API Gateway
-   E-MapReduce
-   HybridDB for MySQL
-   HybridDB for PostgreSQL
-   Express Connect

By clicking on the number of resources, you can view the list page for the corresponding services under Cloud Service Monitoring.

**Note:** To monitor and view ECS data \(such as CPU, memory, and disk usage\), you need to install the CloudMonitor agent. For more information about how to install the CloudMonitor agent, see [Install CloudMonitor agent](../../../../reseller.en-US/User Guide/Host monitoring/Install CloudMonitor agent.md#).

## Alarm overview {#section_cl5_l54_tdb .section}

The alarm overview provides alarm statistics, including the total number of alarms for the past seven days, the number of currently triggered alarm rules, the number of alarm rules with insufficient data, and the alarm SMS usage for the current month.

You can view more information by clicking on the number of alarms or alarm rules.

## Event overview {#section_t4b_gv4_tdb .section}

Event overview summarizes all the exceptions and O&M events that occur during a span of 24 hours. The following are important events that are supported.

|Product|Event|
|:------|:----|
|Host|Agent stops working.|
|ApsaraDB for RDS |Master/Backup switchover|
|ApsaraDB for RDS |Instance failure|
|ApsaraDB for MongoDB|Instance failure|
|ApsaraDB for Redis|Master/Backup switchover|
|ApsaraDB for Redis|Instance failure|

## Resource usage overview {#section_ivr_rw4_tdb .section}

Resource usage shows the overall resource usage of each service under your account. The cumulative usage in the current month is monitored and measured for OSS, CDN, and Log Service. The metrics for all other services are monitored in real time by using the 95th percentile method. For example, if the 95th percentile for the CPU usage of ECS instances is 34%, 95% of the ECS instances have a CPU usage of less than 34%. The value that is determined by this method varies by product.

## Resource indicator descriptions {#section_cfr_sw4_tdb .section}

|Product|Indicator|Statistical method|Statistical period |Statistical range|
|:------|:--------|:-----------------|:------------------|:----------------|
|Host|CPU usage|95th percentile|Real-time|All instances|
|Host|Memory usage|95th percentile|Real-time|All instances|
|Host|Disk usage|95th percentile|Real-time|All instances|
|Host|Outbound Internet bandwidth|95th percentile|Real-time|All instances|
|ApsaraDB for RDS|CPU usage|95th percentile|Real-time|All instances|
|ApsaraDB for RDS|IOPS usage|95th percentile|Real-time|All instances|
|ApsaraDB for RDS|Connection usage|95th percentile|Real-time|All instances|
|ApsaraDB for RDS|Disk usage|95th percentile|Real-time|All instances|
|OSS|Total outbound Internet traffic this month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All buckets|
|OSS|Total number of PUT requests this month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All buckets|
|OSS|Total number of GET requests this month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All buckets|
|OSS|Storage size|Sum| The sum of the storage currently occupied by all OSS buckets|All buckets|
|CDN|Total traffic for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All domain names|
|CDN|Peak network bandwidth|95th percentile|Real-time|All domain names|
|CDN|Access QPS|95th percentile|Real-time|All domain names|
|ApsaraDB for MongoDB|CPU usage|95th percentile|Real-time|All instances|
|ApsaraDB for MongoDB|Memory usage |95th percentile|Real-time|All instances|
|ApsaraDB for MongoDB|IOPS usage|95th percentile|Real-time|All instances|
|ApsaraDB for MongoDB|Connection usage|95th percentile|Real-time|All instances|
|ApsaraDB for MongoDB|Disk usage|95th percentile|Real-time|All instances|
|ApsaraDB for Memcache|Cache hit ratio|95th percentile|Real-time|All instances|
|ApsaraDB for Memcache|Cache usage|95th percentile|Real-time|All instances|
|ApsaraDB for Redis|Memory usage |95th percentile|Real-time|All instances|
|ApsaraDB for Redis|IOPS usage|95th percentile|Real-time|All instances|
|ApsaraDB for Redis|Connection usage|95th percentile|Real-time|All instances|
|EIP|Inbound network bandwidth|95th percentile|Real-time|All instances|
|EIP|Outbound network bandwidth|95th percentile|Real-time|All instances|
|Container Service|CPU usage|95th percentile|Real-time|All instances|
|Container Service|Memory usage |95th percentile|Real-time|All instances|
|Container Service|Outbound Internet traffic|95th percentile|Real-time|All instances|
|Log Service |Total inbound network traffic for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All projects|
|Log Service |Total outbound network traffic for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All projects|
|Log Service|Total requests for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All projects|
|ApsaraDB for HybridDB|CPU usage|95th percentile|Real-time|All instances|
|ApsaraDB for HybridDB|Memory usage |95th percentile|Real-time|All instances|
|ApsaraDB for HybridDB|IOPS usage|95th percentile|Real-time|All instances|
|ApsaraDB for HybridDB|Connection usage|95th percentile|Real-time|All instances|
|ApsaraDB for HybridDB|Disk usage|95th percentile|Real-time|All instances|

