# E-MapReduce {#concept_dcn_bpd_zdb .concept}

By monitoring multiple metrics of E-MapReduce, such as the CPU idle rate, memory capacity, and disk capacity, CloudMonitor helps you to monitor the running status of E-MapReduce. CloudMonitor automatically collects data for E-MapReduce metrics from the time after you purchase the E-MapReduce service.

## Monitoring service {#section_ozm_fpd_zdb .section}

-   **Metrics**

    |Metric|Dimension|Unit|Minimum monitoring granularity|
    |:-----|:--------|:---|:-----------------------------|
    |Inbound traffic rate|User, cluster, and role|bits/s|30s|
    |Outbound network rateNetwork drain Rate|User, cluster, and role|bits/s|30s|
    |CPU idleness|User, cluster, and role|%|1 minute|
    |User-mode CPU usage|User, cluster, and role|%|30s|
    |System-mode CPU usage|User, cluster, and role|%|30s|
    |Idle disk capacity|User, cluster, and role|Bytes|30s|
    |Total disk capacity|User, cluster, and role|Bytes|30s|
    |Average load within 15 minutes|User, cluster, and role|-|30s|
    |Average load within 5 minutes|User, cluster, and role|-|30s|
    |Average load within 1 minutes|User, cluster, and role|-|30s|
    |Idle memory capacity|User, cluster, and role|Bytes|30s|
    |Total memory capacity|User, cluster, and role|Bytes|30s|
    |Inbound data packet rate|User, cluster, and role|Packets/s|30s|
    |Outbound data packet rate|User, cluster, and role|Packets/s|30s|
    |Number of running processes|User, cluster, and role|Processes|30s|
    |Total number of processes |User, cluster, and role|Processes|30s|
    |Number of blocked processes|User, cluster, and role|Processes|30s|
    |Number of created processes/threads|User, cluster, and role|Processes/threads|30s|
    |MemNonHeapUsedM|User, cluster, and role|Bytes|30s|
    |MemNonHeapCommittedM|User, cluster, and role|Bytes|30s|
    |Memnonheapmaxm|User, cluster, and role|Bytes|30s|
    |MemHeapUsedM|User, cluster, and role|Bytes|30s|
    |MemHeapCommittedM|User, cluster, and role|Bytes|30s|
    |MemHeapMaxM|User, cluster, and role|Bytes|30s|
    |MemMaxM|User, cluster, and role|Bytes|30s|
    |Threadsnew|User, cluster, and role|-|30s|
    |ThreadsRunnable|User, cluster, and role|-|30s|
    |ThreadsBlocked|User, cluster, and role|-|30s|
    |ThreadsWaiting|User, cluster, and role|-|30s|
    |ThreadsTimedWaiting|User, cluster, and role|-|30s|
    |ThreadsTerminated|User, cluster, and role|-|30s|
    |GcCount|User, cluster, and role|-|30s|
    |GcTimeMillis|User, cluster, and role|-|30s|
    |CallQueueLength|User, cluster, and role|-|30s|
    |NumOpenConnections|User, cluster, and role|-|30s|
    |ReceivedBytes|User, cluster, and role|-|30s|
    |SentBytes|User, cluster, and role|-|30s|
    |BlockCapacity|User, cluster, and role|-|30s|
    |BlocksTotal|User, cluster, and role|-|30s|
    |CapacityRemaining|User, cluster, and role|-|30s|
    |CapacityTotal|User, cluster, and role|-|30s|
    |CapacityUsed|User, cluster, and role|-|30s|
    |CapacityUsedNonDFS|User, cluster, and role|-|30s|
    |CorruptBlocks|User, cluster, and role|-|30s|
    |ExcessBlocks|User, cluster, and role|-|30s|
    |ExpiredHeartbeats|User, cluster, and role|-|30s|
    |MissingBlocks|User, cluster, and role|-|30s|
    |PendingDataNodeMessageCount|User, cluster, and role|-|30s|
    |PendingDeletionBlocks|User, cluster, and role|-|30s|
    |PendingReplicationBlocks|User, cluster, and role|-|30s|
    |PostponedMisreplicatedBlocks|User, cluster, and role|-|30s|
    |ScheduledReplicationBlocks|User, cluster, and role|-|30s|
    |TotalFiles|User, cluster, and role|-|30s|
    |TotalLoad|User, cluster, and role|-|30s|
    |UnderReplicatedBlocks|User, cluster, and role|-|30s|
    |BlocksRead|User, cluster, and role|-|30s|
    |BlocksRemoved|User, cluster, and role|-|30s|
    |BlocksReplicated|User, cluster, and role|-|30s|
    |BlocksUncached|User, cluster, and role|-|30s|
    |BlocksVerified|User, cluster, and role|-|30s|
    |BlockVerificationFailures|User, cluster, and role|-|30s|
    |BlocksWritten|User, cluster, and role|-|30s|
    |BytesRead|User, cluster, and role|-|30s|
    |BytesWritten|User, cluster, and role|-|30s|
    |FlushNanosAvgTime|User, cluster, and role|-|30s|
    |FlushNanosNumOps|User, cluster, and role|-|30s|
    |FsyncCount|User, cluster, and role|-|30s|
    |VolumeFailures|User, cluster, and role|-|30s|
    |ReadBlockOpNumOps|User, cluster, and role|-|30s|
    |ReadBlockOpAvgTime|User, cluster, and role|ms|30s|
    |WriteBlockOpNumOps|User, cluster, and role|-|30s|
    |WriteBlockOpAvgTime|User, cluster, and role|ms|30s|
    |BlockChecksumOpNumOps|User, cluster, and role|-|30s|
    |BlockChecksumOpAvgTime|User, cluster, and role|ms|30s|
    |CopyBlockOpNumOps|User, cluster, and role|-|30s|
    |CopyBlockOpAvgTime|User, cluster, and role|ms|30s|
    |ReplaceBlockOpNumOps|User, cluster, and role|-|30s|
    |ReplaceBlockOpAvgTime|User, cluster, and role|ms|30s|
    |BlockReportsNumOps|User, cluster, and role|-|30s|
    |BlockReportsAvgTime|User, cluster, and role|ms|30s|
    |NodeManager\_AllocatedContainers|User, cluster, and role|-|30s|
    |ContainersCompleted|User, cluster, and role|-|30s|
    |ContainersFailed|User, cluster, and role|-|30s|
    |ContainersIniting|User, cluster, and role|-|30s|
    |ContainersKilled|User, cluster, and role|-|30s|
    |ContainersLaunched|User, cluster, and role|-|30s|
    |ContainersRunning|User, cluster, and role|-|30s|
    |ActiveApplications|User, cluster, and role|-|30s|
    |ActiveUsers|User, cluster, and role|-|30s|
    |AggregateContainersAllocated|User, cluster, and role|-|30s|
    |AggregateContainersReleased|User, cluster, and role|-|30s|
    |AllocatedContainers|User, cluster, and role|-|30s|
    |AppsCompleted|User, cluster, and role|-|30s|
    |AppsFailed|User, cluster, and role|-|30s|
    |AppsKilled|User, cluster, and role|-|30s|
    |AppsPending|User, cluster, and role|-|30s|
    |AppsRunning|User, cluster, and role|-|30s|
    |AppsSubmitted|User, cluster, and role|-|30s|
    |AvailableMB|User, cluster, and role|-|30s|
    |AvailableVCores|User, cluster, and role|-|30s|
    |PendingContainers|User, cluster, and role|-|30s|
    |ReservedContainers|User, cluster, and role|-|30s|

    **Note:** 

    -   Monitoring data is preserved for at most 31 days.
    -   You can view monitoring data for a maximum of 14 consecutive days.

-   **Viewing monitoring data.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **E-MapReduce**.
    3.  Click an instance name or click Monitoring Chart in the Action column to access the instance monitoring details page and view various metrics.
    4.  Click the **Time Range** toggle button at the top of the page or use the specific selection function. You can view the monitoring data for up to 14 consecutive days.
    5.  Click **Zoom In** in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_z1k_fqd_zdb .section}

-   **Set an alarm rule.**
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **E-MapReduce**.
    3.  Click an instance name or click **Monitoring Chart** in the Action column to access the instance monitoring details page.
    4.  Click the bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all E-MapReduce instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any E-MapReduce instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **5mins CPU Idle rate \>= 10%**, the alarm service will check every five minutes whether the CPU idle rate within five minutes meets or exceeds 10%.

        Consider the following example. For the alarm service in host monitoring, one data point is reported in 15 seconds for a single server metric, and 20 data points in five minutes. This relates to the following alarm rules.

        -   **5mins Average CPU Usage \> 90%**: The average CPU usage value of the 20 data points in five minutes exceeds 90%.
        -   **5mins CPU Usage Always \> 90%**: The CPU usage values of the 20 data points in five minutes all exceed 90%.
        -   **5mins CPU Usage Once \> 90%**: The CPU usage value of at least one of the 20 data points in five minutes exceeds 90%.
        -   **Total 5mins Internet Outbound Traffic \> 50 MB**: The sum of the outbound traffic values of the 20 data points in five minutes exceeds 50 MB.
    -   **Mute For**: the period of time that an alarm is muted so that alarm contacts do not receive any alarm notifications during this period. An alarm rule can be muted for up to 24 hours \(or 1 day\).
    -   **Triggered when threshold is exceeded for**: An alarm notification is sent if the detected values reach the alarm rule threshold a certain number of times consecutively.
    -   **Effective Period**: the period of time for which an alarm rule is effective. During this period of time, the alarm service checks metric data and determines whether to generate an alarm.
    -   **Notification Contact**: a group of contacts who receive alarm notifications.
    -   **Notification Methods**: Emails and DingTalk chatbot.
    -   **Email Subject**: The email subject is set as the product name, metric, and instance ID involved in the alarm by default.
    -   **Email Remark**: supplementary information customized for an alarm email. Remarks are sent as part of the alarm notification email body.
    -    **HTTP CallBack**: Enter a URL accessible through the Internet and CloudMonitor will push the alarm information to the address through a POST request. Currently, only HTTP is supported.

