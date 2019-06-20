# DescribeSystemEventMetaList {#doc_api_Cms_DescribeSystemEventMetaList .reference}

You can call this operation to query the meta information of system events.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSystemEventMetaList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSystemEventMetaList|The operation that you want to perform. Set the value to DescribeSystemEventMetaList.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code.

 |
|Data| | |The detailed meta information.

 |
|└EventType|String|Maintenance|The type of the event. The available event types vary with service.

 |
|└Level|String|INFO|The level of the alert. Valid values:

 -   CRITICAL
-   WARN
-   INFO

 |
|└Name|String|SelectFailureRate|The name of the event.

 |
|└NameDesc|String|High query failure rate|The description of the event name.

 |
|└Product|String|ADS|The abbreviation of the service name.

 |
|└Status|String|failed|The status of the event.

 |
|└StatusDesc|String|Operation Failed|The description of the status.

 |
|Message|String|success|The error message.

 |
|RequestId|String|A6582C8B-E67C-4A19-BC15-EAEFEBDC7995|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSystemEventMetaList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeSystemEventMetaResponse>
  <Data> 
    <Resource>
      <Name>InsertFailureRate</Name>
      <Status>failed</Status>
      <Product>ADS</Product>
      <StatusDesc>Operation Failed</StatusDesc>
      <NameDesc>High insertion failure rate.</NameDesc>
      <Level>INFO</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>SelectFailureRate</Name>
      <Status>failed</Status>
      <Product>ADS</Product>
      <StatusDesc>Operation Failed</StatusDesc>
      <NameDesc>High query failure rate.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>StorageUsage</Name> 
      <Status>failed</Status>
      <Product>ADS</Product>
      <StatusDesc>Operation Failed</StatusDesc>
      <NameDesc>High storage space usage.</NameDesc>
      <Level>WARN</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Agent_Status_Running</Name>
      <Status>running</Status>
      <Product>CloudMonitor</Product>
      <StatusDesc>running</StatusDesc> 
      <NameDesc>Heartbeat check is resumed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Agent_Status_Stopped</Name>
      <Status>stopped</Status>
      <Product>CloudMonitor</Product>
      <StatusDesc>stopped</StatusDesc>
      <NameDesc>Heartbeat check failed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Group_AddResourcesFailed_QuotaReached</Name>
      <Status>failed</Status>
      <Product>CloudMonitor</Product>
      <StatusDesc>failed</StatusDesc>
      <NameDesc>Machines failed to be dynamically added to a group because the resource usage limits have been reached.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>CloseContBackup</Name>
      <Status>failed</Status>
      <Product>DBS</Product>
      <StatusDesc>failed</StatusDesc>
      <NameDesc>Incremental backup is disabled.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>ContBackupFail</Name>
      <Status>failed</Status>
      <Product>DBS</Product>
      <StatusDesc>failed</StatusDesc>
      <NameDesc>An error occurred during incremental backup.</NameDesc>
      <Level>WARN</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>DataRestoreFail</Name>
      <Status>failed</Status>
      <Product>DBS</Product>
      <StatusDesc>failed</StatusDesc>
      <NameDesc>An error occurred during data recovery.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>DataRestoreSuccess</Name>
      <Status>running</Status>
      <Product>DBS</Product>
      <StatusDesc>running</StatusDesc>
      <NameDesc>Data recovery is successful.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>FullBackupFail</Name>
      <Status>failed</Status>
      <Product>DBS</Product>
      <StatusDesc>failed</StatusDesc>
      <NameDesc>An error occurred during full backup.</NameDesc>
      <Level>WARN</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>InstancePause</Name>
      <Status>failed</Status>
      <Product>DBS</Product>
      <StatusDesc>failed</StatusDesc>
      <NameDesc>A backup plan is paused.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>InstanceStart</Name>
      <Status>running</Status>
      <Product>DBS</Product>
      <StatusDesc>running</StatusDesc>
      <NameDesc>A backup plan is started.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>OpenContBackup</Name>
      <Status>running</Status>
      <Product>DBS</Product>
      <StatusDesc>running</StatusDesc>
      <NameDesc>Incremental log backup is enabled.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>StatusCheck</Name>
      <Status>failed</Status>
      <Product>E-MapReduce</Product>
      <StatusDesc>failed</StatusDesc>
      <NameDesc>Service component status.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>Disk:Stalled:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>End of disk performance impact.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Disk:Stalled:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Beginning of disk performance impact.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Disk:StateChange</Name>
      <Status>Normal</Status>
      <Product>ECS</Product>
      <StatusDesc>Normal</StatusDesc>
      <NameDesc>Disk status change notification.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>Image:StateChange</Name>
      <Status>Normal</Status>
      <Product>ECS</Product>
      <StatusDesc>Normal</StatusDesc>
      <NameDesc>Image status change notification.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Delete:Avoided</Name>
      <Status>Avoided</Status>
      <Product>ECS</Product>
      <StatusDesc>Avoided</StatusDesc>
      <NameDesc>Release of pay-as-you-go resources due to an overdue payment is prevented.</NameDesc>
      <Level>INFO</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Delete:Canceled</Name>
      <Status>Canceled</Status>
      <Product>ECS</Product>
      <StatusDesc>Canceled</StatusDesc>
      <NameDesc>Release of pay-as-you-go resources due to an overdue payment is cancelled.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Delete:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Release of pay-as-you-go resources due to an overdue payment is completed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Delete:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Release of pay-as-you-go resources due to an overdue payment is in process.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Delete:Failed</Name>
      <Status>Failed</Status>
      <Product>ECS</Product>
      <StatusDesc>Failed</StatusDesc>
      <NameDesc>Release of pay-as-you-go resources due to an overdue payment failed.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Delete:Scheduled</Name>
      <Status>Scheduled</Status>
      <Product>ECS</Product>
      <StatusDesc>Scheduled</StatusDesc>
      <NameDesc>Release of pay-as-you-go resources due to an overdue payment is scheduled.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.PerformanceAffect:Avoided</Name>
      <Status>Avoided</Status>
      <Product>ECS</Product>
      <StatusDesc>Avoided</StatusDesc>
      <NameDesc>Instance performance degradation due to an overdue payment is prevented.</NameDesc>
      <Level>INFO</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.PerformanceAffect:Canceled</Name>
      <Status>Canceled</Status>
      <Product>ECS</Product>
      <StatusDesc>Canceled</StatusDesc>
      <NameDesc>Instance performance degradation due to an overdue payment is cancelled.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.PerformanceAffect:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Instance performance degradation due to an overdue payment is completed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.PerformanceAffect:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Instance performance degradation due to an overdue payment is in process.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.PerformanceAffect:Failed</Name>
      <Status>Failed</Status>
      <Product>ECS</Product>
      <StatusDesc>Failed</StatusDesc>
      <NameDesc>Instance performance degradation due to an overdue payment is failed.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.PerformanceAffect:Scheduled</Name>
      <Status>Scheduled</Status>
      <Product>ECS</Product>
      <StatusDesc>Scheduled</StatusDesc>
      <NameDesc>Instance performance degradation due to an overdue payment is scheduled.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Stop:Avoided</Name>
      <Status>Avoided</Status>
      <Product>ECS</Product>
      <StatusDesc>Avoided</StatusDesc>
      <NameDesc>Stop of pay-as-you-go resources due to an overdue payment is prevented.</NameDesc>
      <Level>INFO</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Stop:Canceled</Name>
      <Status>Canceled</Status>
      <Product>ECS</Product>
      <StatusDesc>Canceled</StatusDesc>
      <NameDesc>Stop of pay-as-you-go resources due to an overdue payment is cancelled.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Stop:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Stop of pay-as-you-go resources due to an overdue payment is completed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Stop:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Stop of pay-as-you-go resources due to an overdue payment is in process.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Stop:Failed</Name>
      <Status>Failed</Status>
      <Product>ECS</Product>
      <StatusDesc>Failed</StatusDesc>
      <NameDesc>Stop of pay-as-you-go resources due to an overdue payment failed.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:AccountUnbalanced.Stop:Scheduled</Name>
      <Status>Scheduled</Status>
      <Product>ECS</Product>
      <StatusDesc>Scheduled</StatusDesc>
      <NameDesc>Stop of pay-as-you-go resources due to an overdue payment is scheduled.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Delete:Avoided</Name>
      <Status>Avoided</Status>
      <Product>ECS</Product>
      <StatusDesc>Avoided</StatusDesc>
      <NameDesc>Release of resources on expiration of a subscribed instance is prevented.</NameDesc>
      <Level>INFO</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Delete:Canceled</Name>
      <Status>Canceled</Status>
      <Product>ECS</Product>
      <StatusDesc>Canceled</StatusDesc>
      <NameDesc>Release of resources on expiration of a subscribed instance is cancelled.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Delete:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Release of resources on expiration of a subscribed instance is completed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Delete:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Release of resources on expiration of a subscribed instance is in process.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Delete:Failed</Name>
      <Status>Failed</Status>
      <Product>ECS</Product>
      <StatusDesc>Failed</StatusDesc>
      <NameDesc>Release of resources on expiration of a subscribed instance failed.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Delete:Scheduled</Name>
      <Status>Scheduled</Status>
      <Product>ECS</Product>
      <StatusDesc>Scheduled</StatusDesc>
      <NameDesc>Release of resources on expiration of a subscribed instance is scheduled.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Stop:Avoided</Name>
      <Status>Avoided</Status>
      <Product>ECS</Product>
      <StatusDesc>Avoided</StatusDesc>
      <NameDesc>Stop of resources on expiration of a subscribed instance is prevented.</NameDesc>
      <Level>INFO</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Stop:Canceled</Name>
      <Status>Canceled</Status>
      <Product>ECS</Product>
      <StatusDesc>Canceled</StatusDesc>
      <NameDesc>Stop of resources on expiration of a subscribed instance is cancelled.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Stop:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Stop of resources on expiration of a subscribed instance is completed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Stop:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Stop of resources on expiration of a subscribed instance is in process.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Stop:Failed</Name>
      <Status>Failed</Status>
      <Product>ECS</Product>
      <StatusDesc>Failed</StatusDesc>
      <NameDesc>Stop of resources on expiration of a subscribed instance failed.</NameDesc>
      <Level>WARN</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceExpiration.Stop:Scheduled</Name>
      <Status>Scheduled</Status>
      <Product>ECS</Product>
      <StatusDesc>Scheduled</StatusDesc>
      <NameDesc>Stop of resources on expiration of a subscribed instance is scheduled.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType/>
    </Resource>
    <Resource>
      <Name>Instance:InstanceFailure.Reboot:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>End of instance restart due to an instance error.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance:InstanceFailure.Reboot:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Beginning of instance restart due to an instance error.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemFailure.Reboot:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>End of instance restart due to a system error.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemFailure.Reboot:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Beginning of instance restart due to a system error.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.PerformanceImpact:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>End of instance performance impact due to system maintenance.</NameDesc>
      <Level>WARN</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.PerformanceImpact:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Beginning of instance performance impact due to system maintenance.</NameDesc>
      <Level>WARN</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.Reboot:Avoided</Name>
      <Status>Avoided</Status>
      <Product>ECS</Product>
      <StatusDesc>Avoided</StatusDesc>
      <NameDesc>Scheduled instance restart due to system maintenance is prevented.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.Reboot:Canceled</Name>
      <Status>Canceled</Status>
      <Product>ECS</Product>
      <StatusDesc>Canceled</StatusDesc>
      <NameDesc>Scheduled instance restart due to system maintenance is cancelled.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.Reboot:Executed</Name>
      <Status>Executed</Status>
      <Product>ECS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Scheduled instance restart due to system maintenance is completed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.Reboot:Executing</Name>
      <Status>Executing</Status>
      <Product>ECS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Scheduled instance restart due to system maintenance is in process.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.Reboot:Failed</Name>
      <Status>Failed</Status>
      <Product>ECS</Product>
      <StatusDesc>Failed</StatusDesc>
      <NameDesc>Scheduled instance restart due to system maintenance failed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance:SystemMaintenance.Reboot:Scheduled</Name>
      <Status>Scheduled</Status>
      <Product>ECS</Product>
      <StatusDesc>Scheduled</StatusDesc>
      <NameDesc>Notification of scheduled instance restart due to system maintenance.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>NetworkInterface:StateChange</Name>
      <Status>Normal</Status>
      <Product>ECS</Product>
      <StatusDesc>Normal</StatusDesc>
      <NameDesc>NIC status change notification.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALE_IN_ERROR</Name>
      <Status>unnormal</Status>
      <Product>ESS</Product>
      <StatusDesc>unnormal</StatusDesc>
      <NameDesc>The scale-in activity of the scaling group failed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALE_IN_START</Name>
      <Status>normal</Status>
      <Product>ESS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>Beginning of the scale-in activity of the scaling group.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALE_IN_SUCCESS</Name>
      <Status>normal</Status>
      <Product>ESS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The scale-in activity of the scaling group is successful.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALE_OUT_ERROR</Name>
      <Status>unnormal</Status>
      <Product>ESS</Product>
      <StatusDesc>unnormal</StatusDesc>
      <NameDesc>The scale-out activity of the scaling group failed.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALE_OUT_START</Name>
      <Status>normal</Status>
      <Product>ESS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>Beginning of the scale-out activity of the scaling group.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALE_OUT_SUCCESS</Name>
      <Status>normal</Status>
      <Product>ESS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The scale-out activity of the scaling group is successful.</NameDesc>
      <Level>INFO</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALE_REJECT</Name>
      <Status>warn</Status>
      <Product>ESS</Product>
      <StatusDesc>warn</StatusDesc>
      <NameDesc>The scaling activity of the scaling group is rejected.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCALING_GROUP_AVAILABILITY_CHECK</Name>
      <Status>normal</Status>
      <Product>ESS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>Availability check for the scaling group.</NameDesc>
      <Level>WARN</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>AUTOSCALING:SCHEDULE_TASK_EXPIRING</Name>
      <Status>warn</Status>
      <Product>ESS</Product>
      <StatusDesc>warn</StatusDesc>
      <NameDesc>Scheduled task expiration reminder.</NameDesc>
      <Level>WARN</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>RuleEngineProcessFail</Name>
      <Status>failed</Status>
      <Product>IoT</Product>
      <StatusDesc>Failed.</StatusDesc>
      <NameDesc>Rule engine processing failed.</NameDesc>
      <Level>WARN</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failure_End</Name>
      <Status>Executed</Status>
      <Product>MongoDB</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>End of an instance failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failure_Start</Name>
      <Status>Executing</Status>
      <Product>MongoDB</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Beginning of an instance failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>BucketEgressBandwidth</Name>
      <Status>normal</Status>
      <Product>OSS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The downstream bandwidth used by buckets has exceeded the report threshold.</NameDesc>
      <Level>INFO</Level> 
      <EventType>Exception</EventType> 
    </Resource> 
    <Resource> 
      <Name>BucketEgressBandwidthThresholdExceeded</Name> 
      <Status>normal</Status> 
      <Product>OSS</Product> 
      <StatusDesc>normal</StatusDesc> 
      <NameDesc>The downstream bandwidth used by buckets has exceeded the throttling threshold.</NameDesc>
      <Level>WARN</Level> 
      <EventType>Exception</EventType> 
    </Resource> 
    <Resource> 
      <Name>BucketIngressBandwidth</Name> 
      <Status>normal</Status> 
      <Product>OSS</Product> 
      <StatusDesc>normal</StatusDesc> 
      <NameDesc>The upstream bandwidth used by buckets has exceeded the report threshold.</NameDesc>
      <Level>INFO</Level> 
      <EventType>Exception</EventType> 
    </Resource> 
    <Resource> 
      <Name>BucketIngressBandwidthThresholdExceeded</Name> 
      <Status>normal</Status> 
      <Product>OSS</Product> 
      <StatusDesc>normal</StatusDesc> 
      <NameDesc>The upstream bandwidth used by buckets has exceeded the throttling threshold.</NameDesc>
      <Level>WARN</Level> 
      <EventType>Exception</EventType> 
    </Resource> 
    <Resource> 
      <Name>UserEgressBandwidth</Name> 
      <Status>normal</Status> 
      <Product>OSS</Product> 
      <StatusDesc>normal</StatusDesc> 
      <NameDesc>The downstream bandwidth of a user has exceeded the report threshold.</NameDesc>
      <Level>INFO</Level> 
      <EventType>Exception</EventType> 
    </Resource> 
    <Resource> 
      <Name>UserEgressBandwidthThresholdExceeded</Name> 
      <Status>normal</Status> 
      <Product>OSS</Product> 
      <StatusDesc>normal</StatusDesc> 
      <NameDesc>The downstream bandwidth of a user has exceeded the throttling threshold.</NameDesc>
      <Level>WARN</Level> 
      <EventType>Exception</EventType> 
    </Resource> 
    <Resource>
      <Name>UserIngressBandwidth</Name>
      <Status>normal</Status>
      <Product>OSS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The upstream bandwidth of a user has exceeded the report threshold.</NameDesc>
      <Level>INFO</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>UserIngressBandwidthThresholdExceeded</Name>
      <Status>normal</Status>
      <Product>OSS</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The upstream bandwidth of a user has exceeded the throttling threshold.</NameDesc>
      <Level>WARN</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failover</Name>
      <Status>Executed</Status>
      <Product>RDS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Instance failover.</NameDesc>
      <Level>WARN</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failure_End</Name>
      <Status>Executed</Status>
      <Product>RDS</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>End of an instance failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failure_Start</Name>
      <Status>Executing</Status>
      <Product>RDS</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Beginning of an instance failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>SyncStatusAbnormal</Name>
      <Status>Abnormal</Status>
      <Product>RDS</Product>
      <StatusDesc>Abnormal</StatusDesc>
      <NameDesc>An error occurred during synchronization.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failover</Name>
      <Status>Executed</Status>
      <Product>Redis</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>Instance failover.</NameDesc>
      <Level>WARN</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failure_End</Name>
      <Status>Executed</Status>
      <Product>Redis</Product>
      <StatusDesc>Executed</StatusDesc>
      <NameDesc>End of an instance failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>Instance_Failure_Start</Name>
      <Status>Executing</Status>
      <Product>Redis</Product>
      <StatusDesc>Executing</StatusDesc>
      <NameDesc>Beginning of an instance failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource> 
    <Resource>
      <Name>SyncStatusAbnormal</Name>
      <Status>Abnormal</Status>
      <Product>Redis</Product>
      <StatusDesc>Abnormal</StatusDesc>
      <NameDesc>An error occurred during synchronization.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>CertKeyExpired_1</Name>
      <Status>normal</Status>
      <Product>SLB</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The certificate will expire in 1 day.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>CertKeyExpired_15</Name> 
      <Status>normal</Status>
      <Product>SLB</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The certificate will expire in 15 days.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>CertKeyExpired_3</Name>
      <Status>normal</Status>
      <Product>SLB</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The certificate will expire in 3 days.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>CertKeyExpired_30</Name>
      <Status>normal</Status>
      <Product>SLB</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The certificate will expire in 30 days.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>CertKeyExpired_60</Name>
      <Status>normal</Status>
      <Product>SLB</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The certificate will expire in 60 days.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>CertKeyExpired_7</Name>
      <Status>normal</Status>
      <Product>SLB</Product>
      <StatusDesc>normal</StatusDesc>
      <NameDesc>The certificate will expire in 7 days.</NameDesc>
      <Level>WARN</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>AccessGatewayFailover</Name>
      <Status>agwfailover</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Access Gateway Failover</StatusDesc>
      <NameDesc>Access point failover.</NameDesc>
      <Level>INFO</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>ConnectionDisconnect</Name>
      <Status>disconnect</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>disconnect</StatusDesc>
      <NameDesc>The network is disconnected.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>DeviceHacked</Name>
      <Status>hacked</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Hacked</StatusDesc>
      <NameDesc>The device is under attack.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>DeviceLinkDown</Name>
      <Status>linkdown</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Link State Change</StatusDesc>
      <NameDesc>Link failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>DeviceOffline</Name>
      <Status>offline</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Offline</StatusDesc>
      <NameDesc>The device is offline.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>StatusNotification</EventType>
    </Resource>
    <Resource>
      <Name>DeviceOnline</Name>
      <Status>online</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Online</StatusDesc>
      <NameDesc>The device is online.</NameDesc>
      <Level>INFO</Level> 
      <EventType>StatusNotification</EventType> 
    </Resource>
    <Resource>
      <Name>DeviceSwitched</Name>
      <Status>switched</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Role Changed</StatusDesc>
      <NameDesc>Device failover.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>DeviceWanLinkDown</Name>
      <Status>WanLinkDown</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Wan Link Down</StatusDesc>
      <NameDesc>WAN link failure.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Exception</EventType>
    </Resource>
    <Resource>
      <Name>DeviceWanLinkSwitched</Name>
      <Status>WanLinkSwitched</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Wan Link Switched</StatusDesc>
      <NameDesc>WAN link failover.</NameDesc>
      <Level>CRITICAL</Level>
      <EventType>Maintenance</EventType>
    </Resource>
    <Resource>
      <Name>DeviceWanLinkUp</Name>
      <Status>WanLinkUp</Status>
      <Product>SmartAccessGateway</Product>
      <StatusDesc>Device Wan Link Up</StatusDesc>
      <NameDesc>WAN link recovery.</NameDesc>
      <Level>INFO</Level>
      <EventType>Exception</EventType>
    </Resource>
  </Data> 
  <RequestId>A6582C8B-E67C-4A19-BC15-EAEFEBDC7995</RequestId>
  <Success>true</Success> 
</DescribeSystemEventMetaResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":{
		"Resource":[
			{
				"Name":"InsertFailureRate",
				"Status":"failed",
				"Product":"ADS",
				"StatusDesc":"Operation Failed",
				"NameDesc":"High insertion failure rate.",
				"Level":"INFO",
				"EventType":"Maintenance"
			},
			{
				"Name":"SelectFailureRate",
				"Status":"failed",
				"Product":"ADS",
				"StatusDesc":"Operation Failed",
				"NameDesc":"High query failure rate.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"StorageUsage",
				"Status":"failed",
				"Product":"ADS",
				"StatusDesc":"Operation Failed",
				"NameDesc":"High storage space usage.",
				"Level":"WARN",
				"EventType":"Maintenance"
			},
			{
				"Name":"Agent_Status_Running",
				"Status":"running",
				"Product":"CloudMonitor",
				"StatusDesc":"running",
				"NameDesc":"Heartbeat check is resumed.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Agent_Status_Stopped",
				"Status":"stopped",
				"Product":"CloudMonitor",
				"StatusDesc":"stopped",
				"NameDesc":"Heartbeat check failed.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Group_AddResourcesFailed_QuotaReached",
				"Status":"failed",
				"Product":"CloudMonitor",
				"StatusDesc":"failed",
				"NameDesc":"Machines failed to be dynamically added to a group because the resource usage limits have been reached.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"CloseContBackup",
				"Status":"failed",
				"Product":"DBS",
				"StatusDesc":"failed",
				"NameDesc":"Incremental backup is disabled.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"ContBackupFail",
				"Status":"failed",
				"Product":"DBS",
				"StatusDesc":"failed",
				"NameDesc":"An error occurred during incremental backup.",
				"Level":"WARN",
				"EventType":"Exception"
			},
			{
				"Name":"DataRestoreFail",
				"Status":"failed",
				"Product":"DBS",
				"StatusDesc":"failed",
				"NameDesc":"An error occurred during data recovery.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"DataRestoreSuccess",
				"Status":"running",
				"Product":"DBS",
				"StatusDesc":"running",
				"NameDesc":"Data recovery is successful.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"FullBackupFail",
				"Status":"failed",
				"Product":"DBS",
				"StatusDesc":"failed",
				"NameDesc":"An error occurred during full backup.",
				"Level":"WARN",
				"EventType":"Exception"
			},
			{
				"Name":"InstancePause",
				"Status":"failed",
				"Product":"DBS",
				"StatusDesc":"failed",
				"NameDesc":"The scheduled backup is suspended.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"InstanceStart",
				"Status":"running",
				"Product":"DBS",
				"StatusDesc":"running",
				"NameDesc":"The scheduled backup is started.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"OpenContBackup",
				"Status":"running",
				"Product":"DBS",
				"StatusDesc":"running",
				"NameDesc":"Incremental log backup is enabled.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"StatusCheck",
				"Status":"failed",
				"Product":"E-MapReduce",
				"StatusDesc":"failed",
				"NameDesc":"Service component status.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"Disk:Stalled:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"End of disk performance impact.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Disk:Stalled:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Beginning of disk performance impact.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Disk:StateChange",
				"Status":"Normal",
				"Product":"ECS",
				"StatusDesc":"Normal",
				"NameDesc":"Disk status change notification.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"Image:StateChange",
				"Status":"Normal",
				"Product":"ECS",
				"StatusDesc":"Normal",
				"NameDesc":"Image status change notification.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"Instance:AccountUnbalanced.Delete:Avoided",
				"Status":"Avoided",
				"Product":"ECS",
				"StatusDesc":"Avoided",
				"NameDesc":"Release of pay-as-you-go resources due to an overdue payment is prevented.",
				"Level":"INFO",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Delete:Canceled",
				"Status":"Canceled",
				"Product":"ECS",
				"StatusDesc":"Canceled",
				"NameDesc":"Release of pay-as-you-go resources due to an overdue payment is cancelled.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Delete:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"Release of pay-as-you-go resources due to an overdue payment is completed.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Delete:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Release of pay-as-you-go resources due to an overdue payment is in process.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Delete:Failed",
				"Status":"Failed",
				"Product":"ECS",
				"StatusDesc":"Failed",
				"NameDesc":"Release of pay-as-you-go resources due to an overdue payment failed.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Delete:Scheduled",
				"Status":"Scheduled",
				"Product":"ECS",
				"StatusDesc":"Scheduled",
				"NameDesc":"Release of pay-as-you-go resources due to an overdue payment scheduled.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.PerformanceAffect:Avoided",
				"Status":"Avoided",
				"Product":"ECS",
				"StatusDesc":"Avoided",
				"NameDesc":"Instance performance degradation due to an overdue payment is prevented.",
				"Level":"INFO",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.PerformanceAffect:Canceled",
				"Status":"Canceled",
				"Product":"ECS",
				"StatusDesc":"Canceled",
				"NameDesc":"Instance performance degradation due to an overdue payment is cancelled.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.PerformanceAffect:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"Instance performance degradation due to an overdue payment is completed.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.PerformanceAffect:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Instance performance degradation due to an overdue payment is in process.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.PerformanceAffect:Failed",
				"Status":"Failed",
				"Product":"ECS",
				"StatusDesc":"Failed",
				"NameDesc":"Instance performance degradation due to an overdue payment failed.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.PerformanceAffect:Scheduled",
				"Status":"Scheduled",
				"Product":"ECS",
				"StatusDesc":"Scheduled",
				"NameDesc":"Instance performance degradation due to an overdue payment is scheduled.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Stop:Avoided",
				"Status":"Avoided",
				"Product":"ECS",
				"StatusDesc":"Avoided",
				"NameDesc":"Stop of pay-as-you-go resources due to an overdue payment is prevented.",
				"Level":"INFO",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Stop:Canceled",
				"Status":"Canceled",
				"Product":"ECS",
				"StatusDesc":"Canceled",
				"NameDesc":"Stop of pay-as-you-go resources due to an overdue payment is cancelled.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Stop:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"Stop of pay-as-you-go resources due to an overdue payment is completed.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Stop:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Stop of pay-as-you-go resources due to an overdue payment is in process.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Stop:Failed",
				"Status":"Failed",
				"Product":"ECS",
				"StatusDesc":"Failed",
				"NameDesc":"Stop of pay-as-you-go resources due to an overdue payment failed.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:AccountUnbalanced.Stop:Scheduled",
				"Status":"Scheduled",
				"Product":"ECS",
				"StatusDesc":"Scheduled",
				"NameDesc":"Stop of pay-as-you-go resources due to an overdue payment is scheduled.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Delete:Avoided",
				"Status":"Avoided",
				"Product":"ECS",
				"StatusDesc":"Avoided",
				"NameDesc":"Release of resources on expiration of a subscribed instance is prevented.",
				"Level":"INFO",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Delete:Canceled",
				"Status":"Canceled",
				"Product":"ECS",
				"StatusDesc":"Canceled",
				"NameDesc":"Release of resources on expiration of a subscribed instance is cancelled.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Delete:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"Release of resources on expiration of a subscribed instance is completed.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Delete:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Release of resources on expiration of a subscribed instance is in process.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Delete:Failed",
				"Status":"Failed",
				"Product":"ECS",
				"StatusDesc":"Failed",
				"NameDesc":"Release of resources on expiration of a subscribed instance failed.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Delete:Scheduled",
				"Status":"Scheduled",
				"Product":"ECS",
				"StatusDesc":"Scheduled",
				"NameDesc":"Release of resources on expiration of a subscribed instance is scheduled.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Stop:Avoided",
				"Status":"Avoided",
				"Product":"ECS",
				"StatusDesc":"Avoided",
				"NameDesc":"Stop of resources on expiration of a subscribed instance is prevented.",
				"Level":"INFO",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Stop:Canceled",
				"Status":"Canceled",
				"Product":"ECS",
				"StatusDesc":"Canceled",
				"NameDesc":"Stop of resources on expiration of a subscribed instance is cancelled.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Stop:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"Stop of resources on expiration of a subscribed instance is completed.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Stop:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Stop of resources on expiration of a subscribed instance is in process.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Stop:Failed",
				"Status":"Failed",
				"Product":"ECS",
				"StatusDesc":"Failed",
				"NameDesc":"Stop of resources on expiration of a subscribed instance failed.",
				"Level":"WARN",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceExpiration.Stop:Scheduled",
				"Status":"Scheduled",
				"Product":"ECS",
				"StatusDesc":"Scheduled",
				"NameDesc":"Stop of resources on expiration of a subscribed instance is scheduled.",
				"Level":"CRITICAL",
				"EventType":""
			},
			{
				"Name":"Instance:InstanceFailure.Reboot:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":End of instance restart due to an instance error.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance:InstanceFailure.Reboot:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Beginning of instance restart due to an instance error.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance:SystemFailure.Reboot:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":" End of instance restart due to a system error.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance:SystemFailure.Reboot:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Beginning of instance restart due to a system error.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance:SystemMaintenance.PerformanceImpact:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"End of instance performance impact due to system maintenance.",
				"Level":"WARN",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance:SystemMaintenance.PerformanceImpact:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Beginning of instance performance impact due to system maintenance.",
				"Level":"WARN",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance:SystemMaintenance.Reboot:Avoided",
				"Status":"Avoided",
				"Product":"ECS",
				"StatusDesc":"Avoided",
				"NameDesc":"Scheduled instance restart due to system maintenance is prevented.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance:SystemMaintenance.Reboot:Canceled",
				"Status":"Canceled",
				"Product":"ECS",
				"StatusDesc":"Canceled",
				"NameDesc":"Scheduled instance restart due to system maintenance is cancelled.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance:SystemMaintenance.Reboot:Executed",
				"Status":"Executed",
				"Product":"ECS",
				"StatusDesc":"Executed",
				"NameDesc":"Scheduled instance restart due to system maintenance is completed.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance:SystemMaintenance.Reboot:Executing",
				"Status":"Executing",
				"Product":"ECS",
				"StatusDesc":"Executing",
				"NameDesc":"Scheduled instance restart due to system maintenance is in process.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance:SystemMaintenance.Reboot:Failed",
				"Status":"Failed",
				"Product":"ECS",
				"StatusDesc":"Failed",
				"NameDesc":"Scheduled instance restart due to system maintenance failed.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance:SystemMaintenance.Reboot:Scheduled",
				"Status":"Scheduled",
				"Product":"ECS",
				"StatusDesc":"Scheduled",
				"NameDesc":"Notification of scheduled instance restart due to system maintenance.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"NetworkInterface:StateChange",
				"Status":"Normal",
				"Product":"ECS",
				"StatusDesc":"Normal",
				"NameDesc":"NIC status change notification.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALE_IN_ERROR",
				"Status":"unnormal",
				"Product":"ESS",
				"StatusDesc":"unnormal",
				"NameDesc":"The scale-in activity of the scaling group failed to be completed.",
				"Level":"CRITICAL",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALE_IN_START",
				"Status":"normal",
				"Product":"ESS",
				"StatusDesc":"normal",
				"NameDesc":"The scale-in activity of the scaling group has started.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALE_IN_SUCCESS",
				"Status":"normal",
				"Product":"ESS",
				"StatusDesc":"normal",
				"NameDesc":"The scale-in activity of the scaling group is successful.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALE_OUT_ERROR",
				"Status":"unnormal",
				"Product":"ESS",
				"StatusDesc":"unnormal",
				"NameDesc":"The scale-out activity of the scaling group failed to be completed.",
				"Level":"CRITICAL",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALE_OUT_START",
				"Status":"normal",
				"Product":"ESS",
				"StatusDesc":"normal",
				"NameDesc":"The scale-out activity of the scaling group has started.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALE_OUT_SUCCESS",
				"Status":"normal",
				"Product":"ESS",
				"StatusDesc":"normal",
				"NameDesc":"The scale-out activity of the scaling group is successful.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALE_REJECT",
				"Status":"warn",
				"Product":"ESS",
				"StatusDesc":"warn",
				"NameDesc":"The scaling activity of the scaling group is rejected.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AUTOSCALING:SCALING_GROUP_AVAILABILITY_CHECK",
				"Status":"normal",
				"Product":"ESS",
				"StatusDesc":"normal",
				"NameDesc":"Scaling group availability detection.",
				"Level":"WARN",
				"EventType":"Maintenance"
			},
			{
				"Name":"AUTOSCALING:SCHEDULE_TASK_EXPIRING",
				"Status":"warn",
				"Product":"ESS",
				"StatusDesc":"warn",
				"NameDesc":"Scheduled task expiration reminder.",
				"Level":"WARN",
				"EventType":"Maintenance"
			},
			{
				"Name":"RuleEngineProcessFail",
				"Status":"failed",
				"Product":"IoT",
				"StatusDesc":"Failed.",
				"NameDesc":"Rule engine processing failed.",
				"Level":"WARN",
				"EventType":"Exception"
			},
			{
				"Name":"Instance_Failure_End",
				"Status":"Executed",
				"Product":"MongoDB",
				"StatusDesc":"Executed",
				"NameDesc":"End of an instance failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance_Failure_Start",
				"Status":"Executing",
				"Product":"MongoDB",
				"StatusDesc":"Executing",
				"NameDesc":"Beginning of an instance failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"BucketEgressBandwidth",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc": "The downstream bandwidth of a bucket exceeds the reporting threshold ",
				"Level":"INFO",
				"EventType":"Exception"
			},
			{
				"Name":"BucketEgressBandwidthThresholdExceeded",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc":"The downstream bandwidth used by buckets has exceeded the throttling threshold.",
				"Level":"WARN",
				"EventType":"Exception"
			},
			{
				"Name":"BucketIngressBandwidth",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc":"The upstream bandwidth used by buckets has exceeded the report threshold.",
				"Level":"INFO",
				"EventType":"Exception"
			},
			{
				"Name":"BucketIngressBandwidthThresholdExceeded",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc":"The upstream bandwidth used by buckets has exceeded the throttling threshold.",
				"Level":"WARN",
				"EventType":"Exception"
			},
			{
				"Name":"UserEgressBandwidth",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc":"The downstream bandwidth of a user has exceeded the report threshold.",
				"Level":"INFO",
				"EventType":"Exception"
			},
			{
				"Name":"UserEgressBandwidthThresholdExceeded",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc":"The downstream bandwidth of a user has exceeded the throttling threshold.",
				"Level":"WARN",
				"EventType":"Exception"
			},
			{
				"Name":"UserIngressBandwidth",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc":"The upstream bandwidth of a user has exceeded the report threshold.",
				"Level":"INFO",
				"EventType":"Exception"
			},
			{
				"Name":"UserIngressBandwidthThresholdExceeded",
				"Status":"normal",
				"Product":"OSS",
				"StatusDesc":"normal",
				"NameDesc":"The upstream bandwidth of a user has exceeded the throttling threshold.",
				"Level":"WARN",
				"EventType":"Exception"
			},
			{
				"Name":"Instance_Failover",
				"Status":"Executed",
				"Product":"RDS",
				"StatusDesc":"Executed",
				"NameDesc":"Instance failover.",
				"Level":"WARN",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance_Failure_End",
				"Status":"Executed",
				"Product":"RDS",
				"StatusDesc":"Executed",
				"NameDesc":"End of an instance failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance_Failure_Start",
				"Status":"Executing",
				"Product":"RDS",
				"StatusDesc":"Executing",
				"NameDesc":"Beginning of an instance failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"SyncStatusAbnormal",
				"Status":"Abnormal",
				"Product":"RDS",
				"StatusDesc":"Abnormal",
				"NameDesc":"An error occurred during synchronization.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance_Failover",
				"Status":"Executed",
				"Product":"Redis",
				"StatusDesc":"Executed",
				"NameDesc":"Instance failover.",
				"Level":"WARN",
				"EventType":"Maintenance"
			},
			{
				"Name":"Instance_Failure_End",
				"Status":"Executed",
				"Product":"Redis",
				"StatusDesc":"Executed",
				"NameDesc":"End of an instance failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"Instance_Failure_Start",
				"Status":"Executing",
				"Product":"Redis",
				"StatusDesc":"Executing",
				"NameDesc":"Beginning of an instance failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"SyncStatusAbnormal",
				"Status":"Abnormal",
				"Product":"Redis",
				"StatusDesc":"Abnormal",
				"NameDesc":"An error occurred during synchronization.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"CertKeyExpired_1",
				"Status":"normal",
				"Product":"SLB",
				"StatusDesc":"normal",
				"NameDesc":"The certificate will expire in 1 day.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"CertKeyExpired_15",
				"Status":"normal",
				"Product":"SLB",
				"StatusDesc":"normal",
				"NameDesc":"The certificate will expire in 15 days.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"CertKeyExpired_3",
				"Status":"normal",
				"Product":"SLB",
				"StatusDesc":"normal",
				"NameDesc":"The certificate will expire in 3 days.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"CertKeyExpired_30",
				"Status":"normal",
				"Product":"SLB",
				"StatusDesc":"normal",
				"NameDesc":"The certificate will expire in 30 days.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"CertKeyExpired_60",
				"Status":"normal",
				"Product":"SLB",
				"StatusDesc":"normal",
				"NameDesc":"The certificate will expire in 60 days.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"CertKeyExpired_7",
				"Status":"normal",
				"Product":"SLB",
				"StatusDesc":"normal",
				"NameDesc":"The certificate will expire in 7 days.",
				"Level":"WARN",
				"EventType":"StatusNotification"
			},
			{
				"Name":"AccessGatewayFailover",
				"Status":"agwfailover",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Access Gateway Failover",
				"NameDesc":"Access point failover.",
				"Level":"INFO",
				"EventType":"Maintenance"
			},
			{
				"Name":"ConnectionDisconnect",
				"Status":"disconnect",
				"Product":"SmartAccessGateway",
				"StatusDesc":"disconnect",
				"NameDesc":"The network is disconnected.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"DeviceHacked",
				"Status":"hacked",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Hacked",
				"NameDesc":"The device is under attack.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"DeviceLinkDown",
				"Status":"linkdown",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Link State Change",
				"NameDesc":"Link failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"DeviceOffline",
				"Status":"offline",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Offline",
				"NameDesc":"The device is offline.",
				"Level":"CRITICAL",
				"EventType":"StatusNotification"
			},
			{
				"Name":"DeviceOnline",
				"Status":"online",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Online",
				"NameDesc":"The device is online.",
				"Level":"INFO",
				"EventType":"StatusNotification"
			},
			{
				"Name":"DeviceSwitched",
				"Status":"switched",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Role Changed",
				"NameDesc":"Device failover.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"DeviceWanLinkDown",
				"Status":"WanLinkDown",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Wan Link Down",
				"NameDesc":"WAN link failure.",
				"Level":"CRITICAL",
				"EventType":"Exception"
			},
			{
				"Name":"DeviceWanLinkSwitched",
				"Status":"WanLinkSwitched",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Wan Link Switched",
				"NameDesc":"WAN link failover.",
				"Level":"CRITICAL",
				"EventType":"Maintenance"
			},
			{
				"Name":"DeviceWanLinkUp",
				"Status":"WanLinkUp",
				"Product":"SmartAccessGateway",
				"StatusDesc":"Device Wan Link Up",
				"NameDesc":"WAN link recovery.",
				"Level":"INFO",
				"EventType":"Exception"
			}
		]
	},
	"RequestId":"A6582C8B-E67C-4A19-BC15-EAEFEBDC7995",
	"Success":true
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

