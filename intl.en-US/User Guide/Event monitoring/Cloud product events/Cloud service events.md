# Cloud service events {#concept_kkv_wzg_ygb .concept}

This topic describes the cloud service system events that event monitoring supports.

## Elastic Compute Service \(ECS\) system events {#section_i2b_hmk_zdb .section}

For more information about the description of ECS system events, see [Overview of event notifications](../../../../reseller.en-US/Deployment & Maintenance/Event notifications/Overview of event notifications.md#).

|Name|Description|Type|Status|Level|Remarks|
|:---|:----------|----|------|:----|-------|
|Instance:InstanceFailure.Reboot|Beginning of instance restart due to an instance error.|Exception|Executing|CRITICAL| |
|Instance:InstanceFailure.Reboot|End of instance restart due to an instance error.|Exception|Executed|CRITICAL| |
|Instance:SystemFailure.Reboot|Beginning of instance restart due to a system error.|Exception|Executing|CRITICAL| |
|Instance:SystemFailure.Reboot|End of instance restart due to a system error.|Exception|Executed|CRITICAL| |
|Instance:SystemMaintenance.Reboot|An instance restart is scheduled due to system maintenance.|Maintenance|Scheduled|CRITICAL| |
|Instance:SystemMaintenance.Reboot|An instance restart due to system maintenance is averted.|Maintenance|Avoided|CRITICAL| |
|Instance:SystemMaintenance.Reboot|An instance restart due to system maintenance is being executed.|Maintenance|Executing|CRITICAL| |
|Instance:SystemMaintenance.Reboot|An instance restart due to system maintenance is completed.|Maintenance|Executed|CRITICAL| |
|Instance:SystemMaintenance.Reboot|An instance restart due to system maintenance is canceled.|Maintenance|Canceled|CRITICAL| |
|Instance:SystemMaintenance.Reboot|An instance restart due to system maintenance has failed.|Maintenance|Failed|CRITICAL| |
|Disk:Stalled|Beginning of disk performance impact.|Exception|Executing|CRITICAL| |
|Disk:Stalled|End of disk performance impact.|Exception|Executed|CRITICAL| |
|Instance:StateChange|Notification of instance status change.|StatusNotification|Normal|INFO|Event details describe instance status, including Running, Stopped, Expired, Expires Soon, Locked, Stopping, To Be Released, and Deleted \(the instance has been released\). For more information about the instance lifecycle, see [Instance lifecycle](https://partners-intl.aliyun.com/help/doc-detail/25380.htm).|
|Instance:PreemptibleInstanceInterruption|Notification of preemptible instance interruption.|StatusNotification|Normal|WARN|Preemptible instances change to the To Be Released status due to various reasons. For example, the market price is higher than your bid, or the relationship between resource supplies and demand changes. For more information, see [Preemptible instances](https://partners-intl.aliyun.com/help/doc-detail/52088.htm).|
|Snapshot:CreateSnapshotCompleted|The disk snapshot is created.|StatusNotification|Normal|INFO| |

## Server Load Balancer system events {#section_izg_2bh_ygb .section}

|Name|Description|Level|
|:---|:----------|:----|
|CertKeyExpired\_1|The certificate will expire in 1 day.|WARN|
|CertKeyExpired\_3|The certificate will expire in 3 days.|WARN|
|CertKeyExpired\_7|The certificate will expire in 7 days.|WARN|
|CertKeyExpired\_15|The certificate will expire in 15 days.|WARN|
|CertKeyExpired\_30|The certificate will expire in 30 days.|WARN|
|CertKeyExpired\_60|The certificate will expire in 60 days.|WARN|

## Object Storage Service system events {#section_nbk_2bh_ygb .section}

|Name|Description|Level|Remarks|
|:---|:----------|:----|-------|
|BucketEgressBandwidth|The downstream bandwidth that is used by buckets has exceeded the report threshold.|INFO|This event is triggered if the total downstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|BucketEgressBandwidthThresholdExceeded|The downstream bandwidth that is used by a bucket has exceeded the throttling threshold.|WARN|This bucket is subject to regional throttling. Throttling is triggered if the total downstream bandwidth that is used by all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|
|BucketIngressBandwidth|The upstream bandwidth that is used by buckets has exceeded the report threshold.|INFO|This event is triggered if the total upstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|BucketIngressBandwidthThresholdExceeded|The upstream bandwidth that is used by a bucket has exceeded the throttling threshold.|WARN|This bucket is subject to regional throttling. Throttling is triggered if the total upstream bandwidth that is used by of all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in Mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|
|UserEgressBandwidth|The downstream bandwidth of a user has exceeded the report threshold.|INFO|This event is triggered if the total downstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|UserEgressBandwidthThresholdExceeded|The downstream bandwidth of a user has exceeded the throttling threshold.|WARN|Throttling is triggered if the total downstream bandwidth that is used by all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|
|UserIngressBandwidth|The upstream bandwidth of a user has exceeded the report threshold.|INFO|This event is triggered if the total upstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|UserIngressBandwidthThresholdExceeded|The upstream bandwidth of a user has exceeded the throttling threshold.|WARN|Throttling is triggered if the total upstream bandwidth that is used by all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|

## Auto Scaling system events {#section_fjl_2bh_ygb .section}

|Name|Description|Status|Level|
|:---|:----------|:-----|:----|
|AUTOSCALING:SCALE\_IN\_ERROR|The scale-in activity of the scaling group failed.|Unnormal|CRITICAL|
|AUTOSCALING:SCALE\_IN\_SUCCESS|The scale-in activity of the scaling group was successful.|Normal|INFO|
|AUTOSCALING:SCALE\_OUT\_ERROR|The scale-out activity of the scaling group failed.|Unnormal|CRITICAL|
|AUTOSCALING:SCALE\_OUT\_SUCCESS|The scale-out activity of the scaling group was successful.|Normal|INFO|
|AUTOSCALING:SCALE\_REJECT|The scaling activity of the scaling group was rejected.|Warn|WARN|
|AUTOSCALING:SCHEDULE\_TASK\_EXPIRING|Scheduled task expiration reminder.|Warn|WARN|
|AUTOSCALING:SCALE\_OUT\_START|The scale-out activity of the scaling group has started.|normal|INFO|
|AUTOSCALING:SCALE\_IN\_START|The scale-in activity of the scaling group has started.|normal|INFO|

## Alibaba Cloud IoT Platform system events {#section_jpm_2bh_ygb .section}

|Name|Description|Type|Status|Level|
|:---|:----------|----|:-----|:----|
|Account\_Connect\_QPS\_Limit|The number of connection requests per second for the current account has reached the upper limit.|Exception|Fail|WARN|
|Account\_Downlink\_QPS\_Limit|The number of requests per second that the current account sent to devices has reached the upper limit.|Exception|Fail|WARN|
|Account\_RuleEngine\_DataForward\_QPS\_Limit|The number of requests per second that the current account sent to the rule engine has reached the upper limit.|Exception|Fail|WARN|
|Account\_Uplink\_QPS\_Limit|The number of requests per second that the current account published has reached the upper limit.|Exception|Fail|WARN|
|Device\_Downlink\_QPS\_Limit|The downstream QPS of any device has reached the upper limit.|Exception|Fail|WARN|
|Device\_Uplink\_QPS\_Limit|The upstream QPS of any device has reached the upper limit.|Exception|Fail|WARN|

## Smart Access Gateway system events {#section_tvn_2bh_ygb .section}

|Name|Description|Status|Level|
|:---|:----------|:-----|:----|
|AccessGatewayFailover|The access point failed over.|Agwfailover|INFO|
|ConnectionDisconnect|The network is disconnected.|Disconnect|CRITICAL|
|DeviceHacked|The device is under attack.|Hacked|CRITICAL|
|DeviceOffline|The device is offline.|Offline|CRITICAL|
|DeviceOnline|The device is online.|Online|INFO|

## CloudMonitor system events {#section_idp_2bh_ygb .section}

|Name|Description|Status|Level|
|:---|:----------|:-----|:----|
|Group\_AddResourcesFailed\_QuotaReached|Failed to add instances to a group in real time because the resource usage has reached the upper limit.|Failed|CRITICAL|
|Agent\_Status\_Stopped|Heartbeat check failed.|Stopped|CRITICAL|
|Agent\_Status\_Running|Heartbeat check is resumed.|Running|CRITICAL|

## Database Backup system events {#section_nyb_kch_ygb .section}

|Name|Description|Status|Level|
|:---|:----------|:-----|:----|
|CloseContBackup|Incremental backup is disabled.|Failed|INFO|
|ContBackupFail|An exception has occurred during incremental backup.|Failed|WARN|
|DataRestoreFail|An exception has occurred during data recovery.|Failed|WARN|
|DataRestoreSuccess|Data recovery is successful.|Running|WARN|
|FullBackupFail|An error has occurred during full backup.|Failed|WARN|
|InstancePause|The backup plan is suspended.|Failed|INFO|
|InstanceStart|The backup plan has started.|Running|INFO|
|OpenContBackup|Incremental backup is enabled.|Running|INFO|

## Relational Database Service system events {#section_hd2_kch_ygb .section}

|Name|Description|Status|Level|
|:---|:----------|:-----|:----|
|Instance\_Failover|Instance failover occurred.|Executed|WARN|
|Instance\_Failure\_Start|Beginning of an instance failure.|Executing|CRITICAL|
|Instance\_Failure\_End|End of an instance failure.|Executed|CRITICAL|

## ApsaraDB for Redis system events {#section_h4p_jfh_ygb .section}

|Name|Description|Status|Level|
|:---|:----------|:-----|:----|
|Instance\_Failover|Instance failover occurred.|Executed|WARN|
|Instance\_Failure\_Start|Beginning of an instance failure.|Executing|CRITICAL|
|Instance\_Failure\_End|End of an instance failure.|Executed|CRITICAL|

## ApsaraDB for MongoDB system events {#section_ofg_2vd_ghb .section}

|Name|Description|Status|Level|
|:---|:----------|:-----|:----|
|Instance\_Failure\_Start|Beginning of an instance failure.|Executing|CRITICAL|
|Instance\_Failure\_End|End of an instance failure.|Executed|CRITICAL|

## AnalyticDB events {#section_jd3_2vd_ghb .section}

|Name|Description|Level|
|:---|:----------|:----|
|StorageUsage|The disk usage has exceeded 80%.|CRITICAL|
|InsertFailureRate|The insert failure rate is 10%.|CRITICAL|
|SelectFailureRate|The query failure rate is 10%.|CRITICAL|

## Edge Node Service event {#section_m0t_443_ud4 .section}

|Name|Description|Type|Status|Level|
|----|-----------|----|------|-----|
|EnsRegion:NetworkDown:Executing|The edge node failed.|Exception|Executing|CRITICAL|
|EnsRegion: NetworkDown: Executed|The edge node recovered.|Exception|Executed|CRITICAL|
|EnsRegion:NetworkMigration:Scheduled|Network cutover scheduled for the edge node.|Maintenance|Scheduled|WARN|
|EnsRegion:NetworkMigration:Executing|Network cutover is being executed for the edge node.|Maintenance|Executing|CRITICAL|
|EnsRegion:NetworkMigration:Executed|Network cutover is completed for the edge node.|Maintenance|Executed|INFO|
|EnsRegion:NetworkMigration:Canceled|Network cutover is canceled for the edge node.|Maintenance|Canceled|INFO|
|Instance:SystemFailure.Reboot:Executing|The instance is being restarted due to system errors.|Exception|Executing|CRITICAL|
|Instance:SystemFailure.Reboot:Executed|The instance has been restarted due to system errors.|Exception|Executed|CRITICAL|

