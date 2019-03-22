# RAM for CloudMonitor {#concept_z4m_23b_wdb .concept}

[RAM](https://partners-intl.console.aliyun.com/#/ram) permissions are supported in CloudMonitor. Through the integration of the monitoring console with access control features, you can easily and quickly apply permissions for cloud service monitoring data, alarm rule management, alarm contact and alarm contact groups, and event subscription and related features.

**Note:** 

RAM monitoring data queries are supported for the following cloud products:

-   ECS
-   RDS
-   Server Load Balancer
-   OSS
-   CDN
-   ApsaraDB for Memcache
-   EIP
-   ApsaraDB for Redis
-   Message Service
-   Log Service

## Permissions {#section_q2l_5sk_zdb .section}

In RAM, if a user is authorized with read-only permissions for CloudMonitor, the user can only view relevant data, such as the monitoring data and alarm services, but cannot write data. 

## Authentication types {#section_ywc_gtk_zdb .section}

In addition to basic RAM account permission controls, time-based, multi-factor, and IP authentication are supported.

## Resources {#section_hjg_zsk_zdb .section}

Fine-grained resource descriptions are not supported by RAM. The “\*” wildcard is used for resource authorization.

## Operation description {#section_w45_3tk_zdb .section}

-   Monitoring data

    Data query actions are divided into two categories: Product instance lists and CloudMonitor metric data queries. When authorizing a RAM account to log on to the CloudMonitor portal and view metric data, you must also grant the account permissions for the corresponding product’s instance list and metric data query.

    The corresponding actions are listed in the following table.

    |Product|Action|
    |:------|:-----|
    |CMS|QuerMetricList|
    |CMS|QueryMetricLast|
    |ECS|DescribeInstances|
    |RDS|DescribeDBInstances|
    |SLB|DescribeLoadBalancer\*|
    |OSS|ListBuckets|
    |OCS|DescribeInstances|
    |EIP|DescribeEipAddresses|
    |Aliyun Cloud for Redis|DescribeInstances|
    |Message Service|ListQueue|
    |CDN|DescribeUserDomains|


-   Alarm service

    The alarm service provides permission controls for alarm rule management, alarm contact and alarm contact group management, and event subscription and related features.

    The query-related actions are listed in the following table.

    |Action|Description|
    |:-----|:----------|
    |QueryAlarm|Query an alarm rule|
    |QueryAlarmHistory|Query an alarm history|
    |QueryContactGroup|Query a contact group|
    |QueryContact|Query a contact|
    |QuerySms|Query the number of SMSs used|
    |QueryMns|Querying an event subscription configuration|

    The management-related actions are listed in the following table.

    |Action|Description|
    |:-----|:----------|
    |UpdateAlarm|Modify an alarm rule|
    |CreateAlarm|Create an alarm rule|
    |DeleteAlarm|Delete an alarm rule|
    |DisableAlarm|Disable an alarm rule|
    |EnableAlarm|Enable an alarm rule|
    |CreateContact|Create a contact|
    |DeleteContact|Delete a contact|
    |UpdateContact|Modify a contact|
    |SendEmail|Send an email authentication code|
    |SendSms|Send an SMS verification code|
    |CheckEmail|Check an email verification code|
    |CheckSms|Check an SMS verification code|
    |CreateGroup|Create a contact group|
    |DeleteGroup|Delete a contact group|
    |UpdateGroup|Modify a contact group|
    |CreateMns|Create an event subscription|
    |DeleteMns|Delete an event subscription|
    |UpdateMns|Modify an event subscription|


