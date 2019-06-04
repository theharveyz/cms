# E-MapReduce监控 {#concept_dcn_bpd_zdb .concept}

云监控通过监控 E-MapReduce 集群的 CPU 空闲率、内存容量、磁盘容量等监控项，帮助您监测集群的运行状态，并支持您对监控项设置报警规则。

在您购买 E-MapReduce 服务后，云监控会自动对上述监控项收集数据。

## 监控服务 {#section_ozm_fpd_zdb .section}

-   **监控项说明** 

    |监控项|维度|单位|最小监控粒度|
    |:--|:-|:-|:-----|
    |网络流入速率|用户维度、集群维度、角色维度|bit/s|30s|
    |网络流出速率|用户维度、集群维度、角色维度|bit/s|30s|
    |CPU空闲率|用户维度、集群维度、角色维度|%|1分钟|
    |用户态CPU使用率|用户维度、集群维度、角色维度|%|30s|
    |系统态CPU使用率|用户维度、集群维度、角色维度|%|30s|
    |空闲磁盘容量|用户维度、集群维度、角色维度|Byte|30s|
    |磁盘总容量|用户维度、集群维度、角色维度|Byte|30s|
    |15分钟平均负载|用户维度、集群维度、角色维度|-|30s|
    |5分钟平均负载|用户维度、集群维度、角色维度|-|30s|
    |1分钟平均负载|用户维度、集群维度、角色维度|-|30s|
    |空闲内存容量|用户维度、集群维度、角色维度|Byte|30s|
    |总内存容量|用户维度、集群维度、角色维度|Byte|30s|
    |数据包流入速率|用户维度、集群维度、角色维度|个/秒|30s|
    |数据包流出速率|用户维度、集群维度、角色维度|个/秒|30s|
    |运行中的进程数目|用户维度、集群维度、角色维度|个|30s|
    |总进程数目|用户维度、集群维度、角色维度|个|30s|
    |阻塞的进程数目|用户维度、集群维度、角色维度|个|30s|
    |创建的进程/线程数目|用户维度、集群维度、角色维度|个|30s|
    |MemNonHeapUsedM|用户维度、集群维度、角色维度|Byte|30s|
    |MemNonHeapCommittedM|用户维度、集群维度、角色维度|Byte|30s|
    |MemNonHeapMaxM|用户维度、集群维度、角色维度|Byte|30s|
    |MemHeapUsedM|用户维度、集群维度、角色维度|Byte|30s|
    |MemHeapCommittedM|用户维度、集群维度、角色维度|Byte|30s|
    |MemHeapMaxM|用户维度、集群维度、角色维度|Byte|30s|
    |MemMaxM|用户维度、集群维度、角色维度|Byte|30s|
    |ThreadsNew|用户维度、集群维度、角色维度|-|30s|
    |ThreadsRunnable|用户维度、集群维度、角色维度|-|30s|
    |ThreadsBlocked|用户维度、集群维度、角色维度|-|30s|
    |ThreadsWaiting|用户维度、集群维度、角色维度|-|30s|
    |ThreadsTimedWaiting|用户维度、集群维度、角色维度|-|30s|
    |ThreadsTerminated|用户维度、集群维度、角色维度|-|30s|
    |GcCount|用户维度、集群维度、角色维度|-|30s|
    |GcTimeMillis|用户维度、集群维度、角色维度|-|30s|
    |CallQueueLength|用户维度、集群维度、角色维度|-|30s|
    |NumOpenConnections|用户维度、集群维度、角色维度|-|30s|
    |ReceivedByte|用户维度、集群维度、角色维度|-|30s|
    |SentByte|用户维度、集群维度、角色维度|-|30s|
    |BlockCapacity|用户维度、集群维度、角色维度|-|30s|
    |BlocksTotal|用户维度、集群维度、角色维度|-|30s|
    |CapacityRemaining|用户维度、集群维度、角色维度|-|30s|
    |CapacityTotal|用户维度、集群维度、角色维度|-|30s|
    |CapacityUsed|用户维度、集群维度、角色维度|-|30s|
    |CapacityUsedNonDFS|用户维度、集群维度、角色维度|-|30s|
    |CorruptBlocks|用户维度、集群维度、角色维度|-|30s|
    |ExcessBlocks|用户维度、集群维度、角色维度|-|30s|
    |ExpiredHeartbeats|用户维度、集群维度、角色维度|-|30s|
    |MissingBlocks|用户维度、集群维度、角色维度|-|30s|
    |PendingDataNodeMessageCount|用户维度、集群维度、角色维度|-|30s|
    |PendingDeletionBlocks|用户维度、集群维度、角色维度|-|30s|
    |PendingReplicationBlocks|用户维度、集群维度、角色维度|-|30s|
    |PostponedMisreplicatedBlocks|用户维度、集群维度、角色维度|-|30s|
    |ScheduledReplicationBlocks|用户维度、集群维度、角色维度|-|30s|
    |TotalFiles|用户维度、集群维度、角色维度|-|30s|
    |TotalLoad|用户维度、集群维度、角色维度|-|30s|
    |UnderReplicatedBlocks|用户维度、集群维度、角色维度|-|30s|
    |BlocksRead|用户维度、集群维度、角色维度|-|30s|
    |BlocksRemoved|用户维度、集群维度、角色维度|-|30s|
    |BlocksReplicated|用户维度、集群维度、角色维度|-|30s|
    |BlocksUncached|用户维度、集群维度、角色维度|-|30s|
    |BlocksVerified|用户维度、集群维度、角色维度|-|30s|
    |BlockVerificationFailures|用户维度、集群维度、角色维度|-|30s|
    |BlocksWritten|用户维度、集群维度、角色维度|-|30s|
    |ByteRead|用户维度、集群维度、角色维度|-|30s|
    |ByteWritten|用户维度、集群维度、角色维度|-|30s|
    |FlushNanosAvgTime|用户维度、集群维度、角色维度|-|30s|
    |FlushNanosNumOps|用户维度、集群维度、角色维度|-|30s|
    |FsyncCount|用户维度、集群维度、角色维度|-|30s|
    |VolumeFailures|用户维度、集群维度、角色维度|-|30s|
    |ReadBlockOpNumOps|用户维度、集群维度、角色维度|-|30s|
    |ReadBlockOpAvgTime|用户维度、集群维度、角色维度|ms|30s|
    |WriteBlockOpNumOps|用户维度、集群维度、角色维度|-|30s|
    |WriteBlockOpAvgTime|用户维度、集群维度、角色维度|ms|30s|
    |BlockChecksumOpNumOps|用户维度、集群维度、角色维度|-|30s|
    |BlockChecksumOpAvgTime|用户维度、集群维度、角色维度|ms|30s|
    |CopyBlockOpNumOps|用户维度、集群维度、角色维度|-|30s|
    |CopyBlockOpAvgTime|用户维度、集群维度、角色维度|ms|30s|
    |ReplaceBlockOpNumOps|用户维度、集群维度、角色维度|-|30s|
    |ReplaceBlockOpAvgTime|用户维度、集群维度、角色维度|ms|30s|
    |BlockReportsNumOps|用户维度、集群维度、角色维度|-|30s|
    |BlockReportsAvgTime|用户维度、集群维度、角色维度|ms|30s|
    |NodeManager\_AllocatedContainers|用户维度、集群维度、角色维度|-|30s|
    |ContainersCompleted|用户维度、集群维度、角色维度|-|30s|
    |ContainersFailed|用户维度、集群维度、角色维度|-|30s|
    |ContainersIniting|用户维度、集群维度、角色维度|-|30s|
    |ContainersKilled|用户维度、集群维度、角色维度|-|30s|
    |ContainersLaunched|用户维度、集群维度、角色维度|-|30s|
    |ContainersRunning|用户维度、集群维度、角色维度|-|30s|
    |ActiveApplications|用户维度、集群维度、角色维度|-|30s|
    |ActiveUsers|用户维度、集群维度、角色维度|-|30s|
    |AggregateContainersAllocated|用户维度、集群维度、角色维度|-|30s|
    |AggregateContainersReleased|用户维度、集群维度、角色维度|-|30s|
    |AllocatedContainers|用户维度、集群维度、角色维度|-|30s|
    |AppsCompleted|用户维度、集群维度、角色维度|-|30s|
    |AppsFailed|用户维度、集群维度、角色维度|-|30s|
    |AppsKilled|用户维度、集群维度、角色维度|-|30s|
    |AppsPending|用户维度、集群维度、角色维度|-|30s|
    |AppsRunning|用户维度、集群维度、角色维度|-|30s|
    |AppsSubmitted|用户维度、集群维度、角色维度|-|30s|
    |AvailableMB|用户维度、集群维度、角色维度|-|30s|
    |AvailableVCores|用户维度、集群维度、角色维度|-|30s|
    |PendingContainers|用户维度、集群维度、角色维度|-|30s|
    |ReservedContainers|用户维度、集群维度、角色维度|-|30s|

    **说明：** 

    -   监控数据最多保存31天。
    -   最多可连续查看14天的监控数据
-   **查看监控数据** 
    1.  登录[云监控控制台](https://cms-intl.console.aliyun.com)。
    2.  单击左侧导航栏中**云服务监控**下的**E-MapReduce**，进入E-MapReduce监控列表页面。
    3.  单击集群ID或**操作**中的**监控图表**，进入监控图表页面，可查看各项监控指标。
    4.  单击页面上方的**时间范围**快速选择按钮或自定义时间范围，监控数据最长支持查看连续14天的监控数据。
    5.  （可选）单击监控图右上角的放大按钮，可查看监控大图。

## 报警服务 {#section_z1k_fqd_zdb .section}

-   **设置报警规则** 
    1.  登录[云监控控制台](https://cms-intl.console.aliyun.com)。
    2.  单击左侧导航栏中**云服务监控**下的**E-MapReduce**，进入E-MapReduce监控列表页面。
    3.  单击集群ID或**操作**中的**监控图表**，进入监控图表页面。
    4.  单击监控图右上角的铃铛图标或右上角的**创建报警规则**，选择资源范围、根据参数设置报警规则，选择通知方式，单击**确认**即可。
-   **参数说明** 

    报警规则参数相关说明，请参见[报警规则参数说明](intl.zh-CN/用户指南/报警服务/报警规则/报警规则参数说明.md#)。


