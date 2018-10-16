# Features {#concept_n3h_2s4_tdb .concept}

CloudMonitor provides you with an overview of cloud service resource usage, alarms, important events, and resource usage.  It gives you real-time updates on resource occupancy, usage level, and alarms for each cloud service.

## Cloud service overview {#section_sql_ss4_tdb .section}

The Cloud service overview provides a summary of the resources engaged by the hosts \(like ECS and non-ECS hosts on which mainly, CloudMonitor plugin has been installed\), Server Load Balancer, EIP, ApsaraDB for RDS, OSS, CDN, ApsaraDB for  MongoDB, ApsaraDB for Redis, Message Service, Container Service, Log Service, StreamComputer, Analytic DB, API Gateway, E-MapReduce, HybridDB for MySQL, ExpressConnect, and ApsaraDB for HybridDB.  This helps you to know the asset conditions immediately.

You can view Cloud Service Monitoring list page for the corresponding product, once you click cloud service resource quantity tab.

**Note:** To collect ECS instance CPU, memory, and disk usage data, you must install the CloudMonitor plugin.  Follow the [Plugin installation guide](https://www.alibabacloud.com/help/faq-detail/38859.htm) to install CloudMonitor plugin.

## Alarm overview {#section_cl5_l54_tdb .section}

The alarm overview provides alarm statistics for the past seven days. It mainly includes real-time data for the following: Total number of alarm notifications Total number of triggered alarm rules Alarm rules with insufficient data Alarm SMS usage situation for the current month

You can click on the number of active alarm rules for more information.  By clicking on the number of alarm rules with insufficient data, you can view more information.

## Event overview {#section_t4b_gv4_tdb .section}

Event overview summarizes all the defects and O&M events that occur during the span of 24 hours.   Following are the important events that support various products.

|Product Name|Event name|
|:-----------|:---------|
|Host|Plug-in stops|
|ApsaraDB for RDS |Master/Backup switchover|
|ApsaraDB for RDS |Instance fault|
|ApsaraDB for MongoDB|Instance fault|
|ApsaraDB for Redis|Master/Backup switchover|
|ApsaraDB for Redis|Instance fault|

## Resource levels {#section_ivr_rw4_tdb .section}

Resource levels display the overall resource usage conditions of each product in your account.  The cumulative usage in the current month is monitored and measured for OSS, CDN, and Log Service。The metrics for other products are monitored and measured in real time by using the 95th percentile method.

Resource statistical methods 95th percentile

Percentile is a term used in statistics. To find a percentile, data values are arranged in ascending order, and the corresponding cumulative percentile is calculated. Thus, the data value corresponding to a certain percentile is called the ‘xyz’ percentile.

The 95th percentile is the value of the 95th percentile.  For example, the 95th percentile for the CPU usage for all ECS instances is 34%.   For all the ECS instances, 95% of the instance CPU usage values are less than 34%.

Hence, the 95th percentile statistics show the resource consumption level for majority of cloud services.

## Resource indicator descriptions {#section_cfr_sw4_tdb .section}

|Product name|Indicator name|Statistical method|Statistical period |Statistical range|
|:-----------|:-------------|:-----------------|:------------------|:----------------|
|Host|CPU usage|95th Percent|Real-time|All instances|
|Host|Memory usage|95th Percent|Real-time|All instances|
|Host|Disk usage|95th Percent|Real-time|All instances|
|Host|Public Network outbound bandwidth|95th Percent|Real-time|All instances|
|ApsaraDB for RDS|CPU usage|95th Percent|Real-time|All instances|
|ApsaraDB for RDS|IOPS usage|95th Percent|Real-time|All instances|
|ApsaraDB for RDS|Connection usage|95th Percent|Real-time|All instances|
|ApsaraDB for RDS|Disk usage|95th Percent|Real-time|All instances|
|OSS|Total outbound traffic of public network this month|Sum|Cumulative values from 1st day of this month to the current point in time|All Buckets|
|OSS|Total number of put requests this month|Sum|Cumulative values from 1st day of this month to the current point in time|All Buckets|
|OSS|Total number of Get class requests this month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All buckets|
|OSS|Storage size|Sum| The sum of the storage currently occupied by all OSS buckets|All buckets|
|CDN|Total traffic for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All domain names|
|CDN| Peak network bandwidth|95th Percent|Real-time|All domain names|
|CDN| Access QPS|95th Percent|Real-time|All domain names|
|ApsaraDB for MongoDB|CPU usage|95th Percent|Real-time|All instances|
|ApsaraDB for MongoDB|Memory usage |95th Percent|Real-time|All instances|
|ApsaraDB for MongoDB|IOPS usage|95th Percent|Real-time|All instances|
|ApsaraDB for MongoDB|Connection usage|95th Percent|Real-time|All instances|
|ApsaraDB for MongoDB|Disk usage|95th Percent|Real-time|All instances|
|ApsaraDB for Memcahce|Cache hit ratio|95th Percent|Real-time|All instances|
|ApsaraDB for Memcahce|Cache usage|95th Percent|Real-time|All instances|
|ApsaraDB for Redis|Memory usage |95th Percent|Real-time|All instances|
|ApsaraDB for Redis|IOPS usage|95th Percent|Real-time|All instances|
|ApsaraDB for Redis|Connection usage|95th Percent|Real-time|All instances|
|EIP|Incoming Internet bandwidth|95th Percent|Real-time|All instances|
|EIP| Outgoing Internet bandwidth|95th Percent|Real-time|All instances|
|Container Service|CPU utilization|95th Percent|Real-time|All instances|
|Container Service|Memory usage |95th Percent|Real-time|All instances|
|Container Service|Outgoing Internet traffic|95th Percent|Real-time|All instances|
|Log Service |Total incoming network traffic for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All projects|
|Log Service |Total outgoing network traffic for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All projects|
|Log Service| Total requests for current month|Sum|The cumulative value from 00:00 on the first day of the month to the current time|All projects|
|ApsaraDB for HybridDB|CPU utilization|95th Percent|Real-time|All instances|
|ApsaraDB for HybridDB|Memory usage |95th Percent|Real-time|All instances|
|ApsaraDB for HybridDB|IOPS usage|95th Percent|Real-time|All instances|
|ApsaraDB for HybridDB|Connectios usage|95th Percent|Real-time|All instances|
|ApsaraDB for HybridDB|Disk usage|95th Percent|Real-time|All instances|

