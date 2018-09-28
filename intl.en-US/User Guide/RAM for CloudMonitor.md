# RAM for CloudMonitor {#concept_z4m_23b_wdb .concept}

CloudMonitor supports [RAM](https://ram.console.aliyun.com/?spm=a2c4g.11186623.2.4.yZVEW2#/). This allows you to control permissions for Cloud Service Monitoring metric data, alarm rule management, alarm contact and alarm contact group management through sub-accounts.

**Note:** 

Currently, metric data queries are supported for the following cloud products:

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

## Permission description {#section_q2l_5sk_zdb .section}

In RAM system permissions, the Read-only CloudMonitor access permission only authorizes the sub-account to view relevant data, such as metric data and alarm data. 

## Authentication type {#section_ywc_gtk_zdb .section}

In addition to basic sub-account permission control, RAM currently supports time, MFA, and IP authentication.

## Resource description {#section_hjg_zsk_zdb .section}

Currently, RAM does not support fine-grained resource descriptions. Only the “\*” wildcard is used for resource authorization.

## Operation description {#section_w45_3tk_zdb .section}

-   Metric data

    Data query actions are divided into two groups: Product instance list display and CloudMonitor metric data queries. When authorizing a sub-account to log on to the CloudMonitor portal and view metric data, you must also grant the sub-account permissions for the corresponding product’s instance list and metric data query.

    The corresponding actions are listed in the following table.

    |Product name|action|
    |:-----------|:-----|
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


-   Alarm management

    Alarm management includes alarm rule management, alarm contact and alarm contact group management, and event subscription.

    The query-related actions are listed in the following table.

    |Action|Meaning|
    |:-----|:------|
    |QueryAlarm|Query the alarm rule|
    |QueryAlarmHistory|Query the alarm history|
    |QueryContactGroup|Query the contact group|
    |QueryContact|Query the contact|
    |QuerySms|Query the number of SMSs used|
    |QueryMns|Querying the event subscription configuration|

    The management-related actions are listed in the following table.

    |Action|Meaning|
    |:-----|:------|
    |UpdateAlarm|Modify the alarm rule|
    |CreateAlarm|Create the alarm rule|
    |DeleteAlarm|Delete the alarm rule|
    |DisableAlarm|Disable the alarm rule|
    |EnableAlarm|Enable the alarm rule|
    |CreateContact|Create the contact|
    |DeleteContact|Delete the contact|
    |UpdateContact|Modify the contact|
    |SendEmail|Send the email authentication code|
    |SendSms|Send the SMS verification code|
    |CheckEmail|Check the mail verification code|
    |CheckSms|Check the SMS verification code|
    |CreateGroup|Create the contact group|
    |DeleteGroup|Delete the contact group|
    |UpdateGroup|Modify the contact group|
    |CreateMns|Create the event subscription|
    |DeleteMns|Delete the event subscription|
    |UpdateMns|Modify the event subscription|


