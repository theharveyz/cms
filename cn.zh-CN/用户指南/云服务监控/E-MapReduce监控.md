# E-MapReduce监控 {#concept_dcn_bpd_zdb .concept}

云监控通过监控 E-MapReduce 集群的 CPU 空闲率、内存容量、磁盘容量等多个监控项，帮助用户监测集群的运行状态，并支持用户对监控项设置报警规则。用户购买 E-MapReduce 服务后，云监控会自动对上述监控项收集数据。

## 监控服务 {#section_ozm_fpd_zdb .section}

-   监控项

    |监控项|维度|单位|最小监控粒度|
    |:--|:-|:-|:-----|
    |网络流入速率|用户维度、集群维度、角色维度|bits/s|30s|
    |网络流出速率|用户维度、集群维度、角色维度|bits/s|30s|
    |CPU空闲率|用户维度、集群维度、角色维度|%|1分钟|
    |用户态CPU使用率|用户维度、集群维度、角色维度|%|30s|
    |系统态CPU使用率|用户维度、集群维度、角色维度|%|30s|
    |空闲磁盘容量|用户维度、集群维度、角色维度|Bytes|30s|
    |磁盘总容量|用户维度、集群维度、角色维度|Bytes|30s|
    |15分钟平均负载|用户维度、集群维度、角色维度|-|30s|
    |5分钟平均负载|用户维度、集群维度、角色维度|-|30s|
    |1分钟平均负载|用户维度、集群维度、角色维度|-|30s|
    |空闲内存容量|用户维度、集群维度、角色维度|Bytes|30s|
    |总内存容量|用户维度、集群维度、角色维度|Bytes|30s|
    |数据包流入速率|用户维度、集群维度、角色维度|个/秒|30s|
    |数据包流出速率|用户维度、集群维度、角色维度|个/秒|30s|
    |运行中的进程数目|用户维度、集群维度、角色维度|个|30s|
    |总进程数目|用户维度、集群维度、角色维度|个|30s|
    |阻塞的进程数目|用户维度、集群维度、角色维度|个|30s|
    |创建的进程/线程数目|用户维度、集群维度、角色维度|个|30s|
    |MemNonHeapUsedM|用户维度、集群维度、角色维度|Bytes|30s|
    |MemNonHeapCommittedM|用户维度、集群维度、角色维度|Bytes|30s|
    |MemNonHeapMaxM|用户维度、集群维度、角色维度|Bytes|30s|
    |MemHeapUsedM|用户维度、集群维度、角色维度|Bytes|30s|
    |MemHeapCommittedM|用户维度、集群维度、角色维度|Bytes|30s|
    |MemHeapMaxM|用户维度、集群维度、角色维度|Bytes|30s|
    |MemMaxM|用户维度、集群维度、角色维度|Bytes|30s|
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
    |ReceivedBytes|用户维度、集群维度、角色维度|-|30s|
    |SentBytes|用户维度、集群维度、角色维度|-|30s|
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
    |BytesRead|用户维度、集群维度、角色维度|-|30s|
    |BytesWritten|用户维度、集群维度、角色维度|-|30s|
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

    -   用户最多可连续查看14天的监控数据


-   查看监控数据
    1.  登录[云监控控制台](http://cms.console.aliyun.com/#/groups/)。
    2.  进入**云服务监控**下的**E-MapReduce**实例列表。
    3.  点击实例名称或**操作**中的**监控图表**即可进入实例监控详情页面，查看各项指标。
    4.  点击页面上方的**时间范围**快速选择按钮或精确选择功能，监控数据最长支持查看连续14天的监控数据。
    5.  点击监控图右上角的放大按钮，可查看监控大图。

## 报警服务 {#section_z1k_fqd_zdb .section}

-   参数说明
    -   监控项：即 E-MapReduce 服务提供的监控指标。

    -   统计周期：报警系统会按照这个周期检查您对应的监控数据是否超过了报警阈值。例如设置内存使用率报警规则的统计周期为1分钟，则每间隔1分钟会检查一次内存使用率是否超过了阈值。

    -   统计方法：统计方法指对超出阈值范围的设置。统计方法中可以设置平均值、最大值、最小值、求和值。

        1.  平均值：统计周期内监控数据的平均值。例如统计方法选择15分钟内采集的所有监控数据的平均值，则当平均值大于80%时，才算超过阈值。
        2.  最大值：统计周期内监控数据的最大值。例如统计方法选择15分钟内采集的所有监控数据的最大值，则当最大值大于80%时，才算超过阈值。
        3.  最小值：统计周期内监控数据的最小值。例如统计方法选择15分钟内采集的所有监控数据的最小值，则当最小值大于80%时，才算超过阈值。
        4.  求和值：统计周期内监控数据的总和。例如统计方法选择15分钟内采集的所有监控数据的求和值，则当求和值大于80%时，才算超过阈值。流量类指标需要用到此类统计方法。
    -   连续次数：指连续几个统计周期监控项的值持续超过阈值后触发报警。

        例如：设置 CPU 使用率超过80%报警，统计周期为 5 分钟，连续 3 次超过阈值后报警，则第一次探测 CPU 使用率超过 80% 时，不会发出报警通知。5分钟后第二次探测 CPU 使用率超过80%，也不会发出报警。第三次探测仍然超过 80% 时，才会发出报警通知。即从实际数据第一次超过阈值到最终发出报警规则，最少需要消耗的时间为统计周期×\(连续探测次数-1\)=5×\(3-1\)=10分钟。


-   设置单条报警规则
    1.  登录[云监控控制台](http://cms.console.aliyun.com/#/groups/)。
    2.  进入**云服务监控**下的**E-MapReduce**实例列表。
    3.  点击实例名称或**操作**中的**监控图表**即可进入实例监控详情页面。
    4.  点击监控图右上角的铃铛按钮或页面右上角的**新建报警规则**，可对该实例对应的监控项设置报警规则。

