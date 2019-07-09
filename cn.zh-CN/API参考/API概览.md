# API概览 {#doc_14254 .concept}

云监控提供以下相关API接口。

## 云产品时序指标类监控数据 {#section_2an_efo_b0f .section}

|API|描述|
|---|--|
|[DescribeProjectMeta](cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeProjectMeta.md)|查询云监控支持的时序类监控项产品列表。|
|[DescribeMetricLast](cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricLast.md)|查询指定监控对象的最新监控数据。|
|[DescribeMetricMetaList](cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricMetaList.md)|查询云监控开放的时序类监控项的监控项描述。|
|[DescribeMetricList](cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricList.md)|查询指定时间段内的云产品时序指标监控数据。|
|[DescribeMetricData](cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricData.md)|查询指定时间段内的云产品时序指标监控数据。|
|[DescribeMetricTop](cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricTop.md)|查询指定时间段内排序后的云产品时序指标监控数据。|

## 报警联系人组 {#section_7nf_0gm_iio .section}

|API|描述|
|---|--|
|[DescribeContactListByContactGroup](cn.zh-CN/API参考/报警联系人组/DescribeContactListByContactGroup.md)|查询一个报警联系人组下的报警联系人列表。|
|[DeleteContactGroup](cn.zh-CN/API参考/报警联系人组/DeleteContactGroup.md)|删除报警联系人组。|
|[DescribeContactGroupList](cn.zh-CN/API参考/报警联系人组/DescribeContactGroupList.md)|查询报警联系人组列表。|
|[PutContact](cn.zh-CN/API参考/报警联系人组/PutContact.md)|创建或者修改报警联系人信息。|
|[DeleteContact](cn.zh-CN/API参考/报警联系人组/DeleteContact.md)|删除报警联系人。|
|[DescribeContactList](cn.zh-CN/API参考/报警联系人组/DescribeContactList.md)|查询报警联系人列表。|
|[PutContactGroup](cn.zh-CN/API参考/报警联系人组/PutContactGroup.md)|创建或者修改报警联系人组。|

## 时序指标报警规则 {#section_owl_mqn_skf .section}

|API|描述|
|---|--|
|[ListContactGroup](cn.zh-CN/API参考/时序指标报警规则/ListContactGroup.md)|查询云账号下对应的报警规则联系人组。|
|[DescribeProductsOfActiveMetricRule](cn.zh-CN/API参考/时序指标报警规则/DescribeProductsOfActiveMetricRule.md)|查询开通一键告警产品列表。|
|[EnableActiveMetricRule](cn.zh-CN/API参考/时序指标报警规则/EnableActiveMetricRule.md)|启用一键报警产品。|
|[DescribeActiveMetricRuleList](cn.zh-CN/API参考/时序指标报警规则/DescribeActiveMetricRuleList.md)|显示一键报警规则的列表详情。|
|[PutResourceMetricRule](cn.zh-CN/API参考/时序指标报警规则/PutResourceMetricRule.md)|对单个资源的性能指标设置阈值报警规则。|
|[DeleteMetricRules](cn.zh-CN/API参考/时序指标报警规则/DeleteMetricRules.md)|删除一个或者多个报警规则。|
|[DescribeMetricRuleCount](cn.zh-CN/API参考/时序指标报警规则/DescribeMetricRuleCount.md)|分类取得报警规则的数量。|
|[DisableActiveMetricRule](cn.zh-CN/API参考/时序指标报警规则/DisableActiveMetricRule.md)|禁用一键告警。|
|[EnableMetricRules](cn.zh-CN/API参考/时序指标报警规则/EnableMetricRules.md)|启用一个或多个报警规则。|
|[DescribeMetricRuleList](cn.zh-CN/API参考/时序指标报警规则/DescribeMetricRuleList.md)|查询报警规则列表。|
|[DisableMetricRules](cn.zh-CN/API参考/时序指标报警规则/DisableMetricRules.md)|禁用一个或多个报警规则。|
|[CreateGroupMetricRules](cn.zh-CN/API参考/时序指标报警规则/CreateGroupMetricRules.md)|批量创建应用分组报警规则。|
|[DescribeAlertHistoryList](cn.zh-CN/API参考/时序指标报警规则/DescribeAlertHistoryList.md)|查询报警历史详情。|
|[PutGroupMetricRule](cn.zh-CN/API参考/时序指标报警规则/PutGroupMetricRule.md)|创建或者修改组报警规则。|
|[DescribeAlertingMetricRuleResources](cn.zh-CN/API参考/时序指标报警规则/DescribeAlertingMetricRuleResources.md)|查询一个报警规则下正在报警的资源。|
|[PutMetricRuleTargets](cn.zh-CN/API参考/时序指标报警规则/PutMetricRuleTargets.md)|添加或者修改报警规则的目标。|
|[DescribeMetricRuleTargets](cn.zh-CN/API参考/时序指标报警规则/DescribeMetricRuleTargets.md)|查询报警规则关联目标。|
|[DeleteMetricRuleTargets](cn.zh-CN/API参考/时序指标报警规则/DeleteMetricRuleTargets.md)|删除一个报警规则的目标。|
|[CreateMetricRuleResources](cn.zh-CN/API参考/时序指标报警规则/CreateMetricRuleResources.md)|创建一个报警规则关联的资源。|
|[DeleteMetricRuleResources](cn.zh-CN/API参考/时序指标报警规则/DeleteMetricRuleResources.md)|删除报警规则关联的资源。|

## 主机监控 {#section_olf_mvp_jxc .section}

|API|描述|
|---|--|
|[DeleteMonitoringAgentProcess](cn.zh-CN/API参考/主机监控/DeleteMonitoringAgentProcess.md)|删除进程监控。|
|[DescribeMonitoringAgentStatuses](cn.zh-CN/API参考/主机监控/DescribeMonitoringAgentStatuses.md)|查询云监控插件运行状态。|
|[DescribeMonitoringAgentProcesses](cn.zh-CN/API参考/主机监控/DescribeMonitoringAgentProcesses.md)|查询进程监控列表。|
|[DescribeMonitoringAgentAccessKey](cn.zh-CN/API参考/主机监控/DescribeMonitoringAgentAccessKey.md)|查询非阿里云ECS主机安装云监控插件时所需要的AccessKey和AccessSecret。|
|[UninstallMonitoringAgent](cn.zh-CN/API参考/主机监控/UninstallMonitoringAgent.md)|卸载非阿里云主机监控插件。|
|[InstallMonitoringAgent](cn.zh-CN/API参考/主机监控/InstallMonitoringAgent.md)|对指定ECS安装云监控插件。不适用于非阿里云ECS 的服务器。|
|[DescribeMonitoringAgentHosts](cn.zh-CN/API参考/主机监控/DescribeMonitoringAgentHosts.md)|获取安装云监控插件的主机列表。|
|[DescribeMonitoringAgentConfig](cn.zh-CN/API参考/主机监控/DescribeMonitoringAgentConfig.md)|查询云监控插件的配置信息。|
|[CreateMonitorAgentProcess](cn.zh-CN/API参考/主机监控/CreateMonitorAgentProcess.md)|创建进程监控。|

## 应用分组 {#section_chz_cff_aqu .section}

|API|描述|
|---|--|
|[CreateMonitorGroupNotifyPolicy](cn.zh-CN/API参考/应用分组/CreateMonitorGroupNotifyPolicy.md)|创建暂停应用分组报警通知的策略。|
|[DeleteMonitorGroupNotifyPolicy](cn.zh-CN/API参考/应用分组/DeleteMonitorGroupNotifyPolicy.md)|删除指定应用分组的报警通知暂停策略。|
|[DescribeMonitorGroupNotifyPolicyList](cn.zh-CN/API参考/应用分组/DescribeMonitorGroupNotifyPolicyList.md)|查询应用分组的报警通知暂停策略列表。|
|[DeleteMonitorGroupInstances](cn.zh-CN/API参考/应用分组/DeleteMonitorGroupInstances.md)|删除应用分组内的资源实例。|
|[PutMonitorGroupDynamicRule](cn.zh-CN/API参考/应用分组/PutMonitorGroupDynamicRule.md)|创建或者修改一个应用分组的动态规则，满足规则描述的资源会自动添加到应用分组中。|
|[DeleteMonitorGroupDynamicRule](cn.zh-CN/API参考/应用分组/DeleteMonitorGroupDynamicRule.md)|删除指定应用分组的动态规则。|
|[ModifyMonitorGroupInstances](cn.zh-CN/API参考/应用分组/ModifyMonitorGroupInstances.md)|修改应用分组中的资源。|
|[DescribeMonitorGroupDynamicRules](cn.zh-CN/API参考/应用分组/DescribeMonitorGroupDynamicRules.md)|查询应用分组动态规则的列表。|
|[DescribeMonitorGroupInstanceAttribute](cn.zh-CN/API参考/应用分组/DescribeMonitorGroupInstanceAttribute.md)|查询应用分组的资源实例详情。|
|[DescribeMonitorGroupCategories](cn.zh-CN/API参考/应用分组/DescribeMonitorGroupCategories.md)|查询指定应用分组的产品资源列表和每个产品的资源数量。|
|[CreateMonitorGroup](cn.zh-CN/API参考/应用分组/CreateMonitorGroup.md)|创建一个应用分组。|
|[CreateMonitorGroupInstances](cn.zh-CN/API参考/应用分组/CreateMonitorGroupInstances.md)|添加资源到应用分组。|
|[DescribeMonitorGroups](cn.zh-CN/API参考/应用分组/DescribeMonitorGroups.md)|查询应用分组列表。|
|[ModifyMonitorGroup](cn.zh-CN/API参考/应用分组/ModifyMonitorGroup.md)|修改应用分组。|
|[DescribeMonitorGroupInstances](cn.zh-CN/API参考/应用分组/DescribeMonitorGroupInstances.md)|查询指定应用分组内包含的资源列表。|
|[DeleteMonitorGroup](cn.zh-CN/API参考/应用分组/DeleteMonitorGroup.md)|删除指定的应用分组。|

## 可用性监控 {#section_xdu_c4k_lft .section}

|API|描述|
|---|--|
|[CreateHostAvailability](cn.zh-CN/API参考/可用性监控/CreateHostAvailability.md)|创建可用性监控任务。|
|[DeleteHostAvailability](cn.zh-CN/API参考/可用性监控/DeleteHostAvailability.md)|删除可用性监控任务。|
|[ModifyHostAvailability](cn.zh-CN/API参考/可用性监控/ModifyHostAvailability.md)|修改可用性监控任务。|
|[EnableHostAvailability](cn.zh-CN/API参考/可用性监控/EnableHostAvailability.md)|启用可用性监控任务。|
|[DescribeHostAvailabilityList](cn.zh-CN/API参考/可用性监控/DescribeHostAvailabilityList.md)|查询可用性监控任务列表。|
|[DescribeUnhealthyHostAvailability](cn.zh-CN/API参考/可用性监控/DescribeUnhealthyHostAvailability.md)|查询探测结果异常的服务器列表。|
|[DisableHostAvailability](cn.zh-CN/API参考/可用性监控/DisableHostAvailability.md)|禁用一个可用性监控任务。|

## 全局配置 {#section_ayj_sh5_xmd .section}

|API|描述|
|---|--|
|[DescribeMonitoringConfig](cn.zh-CN/API参考/全局配置/DescribeMonitoringConfig.md)|查询云监控全局配置，例如开启自动安装云监控插件以及一键告警等。|
|[PutMonitoringConfig](cn.zh-CN/API参考/全局配置/PutMonitoringConfig.md)|设置云监控插件全局配置，例如开始自动安装插件以及一键报警等。|

## 云产品事件类监控数据 {#section_v21_woh_kwd .section}

|API|描述|
|---|--|
|[DescribeSystemEventHistogram](cn.zh-CN/API参考/云产品事件类监控数据/DescribeSystemEventHistogram.md)|查询系统事件的时段数量分布图（柱状图）。|
|[SendDryRunSystemEvent](cn.zh-CN/API参考/云产品事件类监控数据/SendDryRunSystemEvent.md)|触发一个用于调试的系统事件，用于调试事件下游配置的触发逻辑是否符合预期。|
|[DescribeSystemEventMetaList](cn.zh-CN/API参考/云产品事件类监控数据/DescribeSystemEventMetaList.md)|查询系统事件的Meta信息。|
|[DescribeSystemEventCount](cn.zh-CN/API参考/云产品事件类监控数据/DescribeSystemEventCount.md)|查询各个产品指定时间段内事件的数量。|
|[DescribeSystemEventAttribute](cn.zh-CN/API参考/云产品事件类监控数据/DescribeSystemEventAttribute.md)|查询系统事件详情。|

## 时序指标报警模板 {#section_siq_oq6_bd1 .section}

|API|描述|
|---|--|
|[ApplyMetricRuleTemplate](cn.zh-CN/API参考/时序指标报警模板/ApplyMetricRuleTemplate.md)|将报警模板应用到分组，生成报警规则。|
|[DescribeMetricRuleTemplateAttribute](cn.zh-CN/API参考/时序指标报警模板/DescribeMetricRuleTemplateAttribute.md)|查询报警模板的详情。|
|[ModifyMetricRuleTemplate](cn.zh-CN/API参考/时序指标报警模板/ModifyMetricRuleTemplate.md)|修改报警模板。|
|[DescribeMetricRuleTemplateList](cn.zh-CN/API参考/时序指标报警模板/DescribeMetricRuleTemplateList.md)|查询报警模板列表。|
|[CreateMetricRuleTemplate](cn.zh-CN/API参考/时序指标报警模板/CreateMetricRuleTemplate.md)|创建报警规则模板。|
|[DeleteMetricRuleTemplate](cn.zh-CN/API参考/时序指标报警模板/DeleteMetricRuleTemplate.md)|删除报警规则模板。|

## 事件报警规则 {#section_k8r_gz3_upp .section}

|API|描述|
|---|--|
|[DescribeEventRuleAttribute](cn.zh-CN/API参考/事件报警规则/DescribeEventRuleAttribute.md)|查询指定规则的详情。|
|[PutEventRuleTargets](cn.zh-CN/API参考/事件报警规则/PutEventRuleTargets.md)|添加或者修改规则的发送目标。|
|[DeleteEventRuleTargets](cn.zh-CN/API参考/事件报警规则/DeleteEventRuleTargets.md)|删除事件报警通知目标。|
|[EnableEventRules](cn.zh-CN/API参考/事件报警规则/EnableEventRules.md)|启用一个或者多个事件监控报警规则。|
|[DescribeEventRuleList](cn.zh-CN/API参考/事件报警规则/DescribeEventRuleList.md)|查询事件报警的列表。|
|[DeleteEventRules](cn.zh-CN/API参考/事件报警规则/DeleteEventRules.md)|删除事件报警规则。|
|[DisableEventRules](cn.zh-CN/API参考/事件报警规则/DisableEventRules.md)|禁用一个或者多个事件报警规则。|
|[PutEventRule](cn.zh-CN/API参考/事件报警规则/PutEventRule.md)|创建或者修改事件的报警规则。|
|[DescribeEventRuleTargetList](cn.zh-CN/API参考/事件报警规则/DescribeEventRuleTargetList.md)|查询指定事件报警规则的报警目标。|

## 自定义监控 {#section_syb_wla_wgb .section}

|API|描述|
|---|--|
|[PutCustomMetric](cn.zh-CN/API参考/自定义监控/PutCustomMetric.md)|上报自定义监控数据。|
|[DescribeCustomMetricList](cn.zh-CN/API参考/自定义监控/DescribeCustomMetricList.md)|查询上报的自定义监控数据。|
|[DeleteCustomMetric](cn.zh-CN/API参考/自定义监控/DeleteCustomMetric.md)|删除自定义监控上报数据。|

## 自定义事件 {#section_b6o_awv_ota .section}

|API|描述|
|---|--|
|[DescribeCustomEventCount](cn.zh-CN/API参考/自定义事件/DescribeCustomEventCount.md)|查询自定义事件的统计结果。|
|[DescribeCustomEventAttribute](cn.zh-CN/API参考/自定义事件/DescribeCustomEventAttribute.md)|查询自定义事件的详情。|
|[DescribeCustomEventHistogram](cn.zh-CN/API参考/自定义事件/DescribeCustomEventHistogram.md)|查询自定义上报的事件的分时段数量分布图。|
|[PutCustomEvent](cn.zh-CN/API参考/自定义事件/PutCustomEvent.md)|上报自定义事件数据监控数据。|

## 站点监控 {#section_sey_uiw_soa .section}

|API|描述|
|---|--|
|[DisableSiteMonitors](cn.zh-CN/API参考/站点监控/DisableSiteMonitors.md)|禁用一个或者多个站点监控探测任务。|
|[DescribeSiteMonitorQuota](cn.zh-CN/API参考/站点监控/DescribeSiteMonitorQuota.md)|查询站点监控的配额以及版本。|
|[DescribeSiteMonitorAttribute](cn.zh-CN/API参考/站点监控/DescribeSiteMonitorAttribute.md)|查询站点监控详细信息。|
|[DeleteSiteMonitors](cn.zh-CN/API参考/站点监控/DeleteSiteMonitors.md)|删除站点监控的探测任务。|
|[DescribeSiteMonitorISPCityList](cn.zh-CN/API参考/站点监控/DescribeSiteMonitorISPCityList.md)|查询可用于创建任务的探测点列表。|
|[DescribeSiteMonitorData](cn.zh-CN/API参考/站点监控/DescribeSiteMonitorData.md)|查询任务的细粒度监控数据。|
|[DescribeSiteMonitorStatistics](cn.zh-CN/API参考/站点监控/DescribeSiteMonitorStatistics.md)|查询指定任务一段时间内的平均统计数据。|
|[CreateSiteMonitor](cn.zh-CN/API参考/站点监控/CreateSiteMonitor.md)|创建站点监控的探测任务。|
|[ModifySiteMonitor](cn.zh-CN/API参考/站点监控/ModifySiteMonitor.md)|修改站点监控探测任务。|
|[EnableSiteMonitors](cn.zh-CN/API参考/站点监控/EnableSiteMonitors.md)|启用一个或者多个站点监控探测任务。|
|[DescribeSiteMonitorList](cn.zh-CN/API参考/站点监控/DescribeSiteMonitorList.md)|查询站点监控任务列表。|

