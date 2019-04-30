# Cloud service events {#concept_kkv_wzg_ygb .concept}

This topic describes the cloud service system events that are supported by event monitoring.

## Elastic Compute Service system events {#section_i2b_hmk_zdb .section}

|Name|Meaning|State|Level|Remarks|
|:---|:------|-----|:----|-------|
|Instance:InstanceFailure.Reboot|Beginning of instance restart due to an instance error.|Executing|CRITICAL| |
|Instance:InstanceFailure.Reboot|End of instance restart due to an instance error.|Executed|CRITICAL| |
|Instance:SystemFailure.Reboot|Beginning of instance restart due to a system error.|Executing|CRITICAL| |
|Instance:SystemFailure.Reboot|End of instance restart due to a system error.|Executed|CRITICAL| |
|Instance:SystemMaintenance.Reboot|An instance restart is scheduled due to system maintenance.|Scheduled|CRITICAL| |
|Instance:SystemMaintenance.Reboot|The instance restart due to system maintenance is prevented.|Avoided|CRITICAL| |
|Instance:SystemMaintenance.Reboot|The instance restart due to system maintenance is being executed.|Executing|CRITICAL| |
|Instance:SystemMaintenance.Reboot|The instance restart due to system maintenance is completed.|Executed|CRITICAL| |
|Instance:SystemMaintenance.Reboot|The instance restart due to system maintenance is canceled.|Canceled|CRITICAL| |
|Instance:SystemMaintenance.Reboot|The instance restart due to system maintenance has failed.|Failed|CRITICAL| |
|Disk:Stalled|Beginning of disk performance impact.|Executing|CRITICAL| |
|Disk:Stalled|End of disk performance impact.|Executed|CRITICAL| |
|Instance: StateChange|Notification of instance state change.|Normal|INFO|The instance state is displayed in event details, including Running, Stopped \(Stopped, Expired, About to Expire, Locked, Releasing, and Pending Release\), and Deleted \(the instance has been released\). For more information about the instance lifecycle, see [Instance lifecycle](https://partners-intl.aliyun.com/help/doc-detail/25380.htm).|
|Instance:PreemptibleInstanceInterruption|Notification of preemptible instance interruption.|Normal|WARN|Preemptible instances enter the Pending Release state for certain reasons. The reasons include the market price is higher than your bid and the relationship between resource supply and demand changes. For more information, see [Preemptible instance](https://partners-intl.aliyun.com/help/doc-detail/52088.htm).|

## Server Load Balancer system events {#section_izg_2bh_ygb .section}

|Name|Meaning|Level|
|:---|:------|:----|
|CertKeyExpired\_1|The certificate will expire in 1 day.|WARN|
|CertKeyExpired\_3|The certificate will expire in 3 days.|WARN|
|CertKeyExpired\_7|The certificate will expire in 7 days.|WARN|
|CertKeyExpired\_15|The certificate will expire in 15 days.|WARN|
|CertKeyExpired\_30|The certificate will expire in 30 days.|WARN|
|CertKeyExpired\_60|The certificate will expire in 60 days.|WARN|

## Object Storage Service system events {#section_nbk_2bh_ygb .section}

|Name|Meaning|Level|Remarks|
|:---|:------|:----|-------|
|BucketEgressBandwidth|The downstream bandwidth that is used by buckets has exceeded the report threshold.|INFO|This event is triggered if the total downstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|BucketEgressBandwidthThresholdExceeded|The downstream bandwidth that is used by a bucket has exceeded the throttling threshold.|WARN|This bucket is subject to regional throttling. Throttling is triggered if the total downstream bandwidth that is used by all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|
|BucketIngressBandwidth|The upstream bandwidth that is used by buckets has exceeded the report threshold.|INFO|This event is triggered if the total upstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|BucketIngressBandwidthThresholdExceeded|The upstream bandwidth that is used by a bucket has exceeded the throttling threshold.|WARN|This bucket is subject to regional throttling. Throttling is triggered if the total upstream bandwidth that is used by of all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in Mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|
|UserEgressBandwidth|The downstream bandwidth of a user has exceeded the report threshold.|INFO|This event is triggered if the total downstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|UserEgressBandwidthThresholdExceeded|The downstream bandwidth of a user has exceeded the throttling threshold.|WARN|Throttling is triggered if the total downstream bandwidth that is used by all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|
|UserIngressBandwidth|The upstream bandwidth of a user has exceeded the report threshold.|INFO|This event is triggered if the total upstream bandwidth that is used by all the buckets owned by a user exceeds the report threshold of 128 Mbit/s.|
|UserIngressBandwidthThresholdExceeded|The upstream bandwidth of a user has exceeded the throttling threshold.|WARN|Throttling is triggered if the total upstream bandwidth that is used by all the buckets in a region exceeds the throttling threshold. Alibaba Cloud throttling threshold is 10 Gbit/s for each region in mainland China, and 5 Gbit/s for Hong Kong and overseas regions by default. No bucket-level throttling threshold is configured by default.|

## Auto Scaling system events {#section_fjl_2bh_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|AUTOSCALING:SCALE\_IN\_ERROR|The scale-in activity of the scaling group failed to be completed.|Unnormal|CRITICAL|
|AUTOSCALING:SCALE\_IN\_SUCCESS|The scale-in activity of the scaling group was successful.|Normal|INFO|
|AUTOSCALING:SCALE\_OUT\_ERROR|The scale-out activity of the scaling group failed to be completed.|Unnormal|CRITICAL|
|AUTOSCALING:SCALE\_OUT\_SUCCESS|The scale-out activity of the scaling group was successful.|Normal|INFO|
|AUTOSCALING:SCALE\_REJECT|The scaling activity of the scaling group was rejected.|Warn|WARN|
|AUTOSCALING:SCHEDULE\_TASK\_EXPIRING|Scheduled task expiration reminder.|Warn|WARN|
|AUTOSCALING:SCALE\_OUT\_START|The scale-out activity of the scaling group has started.|normal|INFO|
|AUTOSCALING:SCALE\_IN\_START|The scale-in activity of the scaling group has started.|normal|INFO|

## Alibaba Cloud IoT system events {#section_jpm_2bh_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|RuleEngineProcessFail|Rule Engine processing failed to be completed.|Failed|WARN|

## Smart Access Gateway system events {#section_tvn_2bh_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|AccessGatewayFailover|The access point fails over.|Agwfailover|INFO|
|ConnectionDisconnect|The network is disconnected.|Disconnect|CRITICAL|
|DeviceHacked|The device is under attack.|Hacked|CRITICAL|
|DeviceOffline|The device is offline.|Offline|CRITICAL|
|DeviceOnline|The device is online.|Online|INFO|

## CloudMonitor system events {#section_idp_2bh_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|Group\_AddResourcesFailed\_QuotaReached|Machines failed to be dynamically added to a group because the resource usage limits have been reached.|Failed|CRITICAL|
|Agent\_Status\_Stopped|Heartbeat check failed.|Stopped|CRITICAL|
|Agent\_Status\_Running|Heartbeat check is resumed.|Running|CRITICAL|

## Database Backup system events {#section_nyb_kch_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|CloseContBackup|Incremental backup is disabled.|Failed|INFO|
|ContBackupFail|An exception has occurred during incremental backup.|Failed|WARN|
|DataRestoreFail|An exception has occurred during data recovery.|Failed|WARN|
|DataRestoreSuccess|Data recovery is successful.|Running|WARN|
|FullBackupFail|An error has occurred during full backup.|Failed|WARN|
|InstancePause|The scheduled backup plan is suspended.|Failed|INFO|
|InstanceStart|The scheduled backup plan has started.|Running|INFO|
|OpenContBackup|Incremental log backup is enabled.|Running|INFO|

## Relational Database Service system events {#section_hd2_kch_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|Instance\_Failover|Instance failover|Executed|WARN|
|Instance\_Failure\_Start|Beginning of an instance failure|Executing|CRITICAL|
|Instance\_Failure\_End|End of an instance failure|Executed|CRITICAL|

## ApsaraDB RDS for Redis system events {#section_h4p_jfh_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|Instance\_Failover|Instance failover|Executed|WARN|
|Instance\_Failure\_Start|Beginning of an instance failure|Executing|CRITICAL|
|Instance\_Failure\_End|End of an instance failure|Executed|CRITICAL|

## ApsaraDB RDS for MongoDB system events {#section_cyx_kfh_ygb .section}

|Name|Meaning|State|Level|
|:---|:------|:----|:----|
|Instance\_Failure\_Start|Beginning of an instance failure|Executing|CRITICAL|
|Instance\_Failure\_End|End of an instance failure|Executed|CRITICAL|

