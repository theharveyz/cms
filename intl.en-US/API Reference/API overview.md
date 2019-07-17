# API overview {#doc_14254 .concept}

The following tables list API operations available for use in CloudMonitor. For more information, see OpenAPI Explorer.

## Monitoring data on time series metrics of cloud services {#section_2xy_e7n_i8e .section}

|Operation|Description|
|---------|-----------|
|[DescribeProjectMeta](intl.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeProjectMeta.md)|Queries detailed information of the monitored cloud services, including service descriptions, namespace, and labels.|
|[DescribeMetricLast](intl.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricLast.md)|Queries the latest monitoring data of a monitored object.|
|[DescribeMetricMetaList](intl.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricMetaList.md)|Queries the descriptions of time series metrics available in CloudMonitor.|
|[DescribeMetricList](intl.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricList.md)|Queries the monitoring data on time series metrics of cloud services in a specified period.|
|[DescribeMetricData](intl.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricData.md)|Queries the monitoring data on time series metrics of cloud services in a specified period.|
|[DescribeMetricTop](intl.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricTop.md)|Queries the monitoring data on time series metrics of cloud services sorted by specified fields in a specified period.|

## Alert group {#section_2n5_b7f_0qs .section}

|Operation|Description|
|---------|-----------|
|[DescribeContactListByContactGroup](intl.en-US/API Reference/Alert contact group/DescribeContactListByContactGroup.md)|Queries alert contacts in an alert group.|
|[DeleteContactGroup](intl.en-US/API Reference/Alert contact group/DeleteContactGroup.md)|Deletes an alert group.|
|[DescribeContactGroupList](intl.en-US/API Reference/Alert contact group/DescribeContactGroupList.md)|Queries alert contact groups.|
|[PutContact](intl.en-US/API Reference/Alert contact group/PutContact.md)|Creates or modifies an alert contact.|
|[DeleteContact](intl.en-US/API Reference/Alert contact group/DeleteContact.md)|Deletes an alert contact.|
|[DescribeContactList](intl.en-US/API Reference/Alert contact group/DescribeContactList.md)|Queries alert contacts.|
|[PutContactGroup](intl.en-US/API Reference/Alert contact group/PutContactGroup.md)|Creates or modifies an alert group.|

## Alert rules for time series metrics {#section_5xu_7jj_jma .section}

|Operation|Description|
|---------|-----------|
|[ListContactGroup](intl.en-US/API Reference/Alert rules for time series metrics/ListContactGroup.md)|Queries the contact groups associated with alert rules under an Alibaba Cloud account.|
|[DescribeProductsOfActiveMetricRule](intl.en-US/API Reference/Alert rules for time series metrics/DescribeProductsOfActiveMetricRule.md)|Queries the services for which one-click alert is enabled.|
|[EnableActiveMetricRule](intl.en-US/API Reference/Alert rules for time series metrics/EnableActiveMetricRule.md)|Enables one-click alert for a service.|
|[DescribeActiveMetricRuleList](intl.en-US/API Reference/Alert rules for time series metrics/DescribeActiveMetricRuleList.md)|Queries details about one-click alert rules.|
|[PutResourceMetricRule](intl.en-US/API Reference/Alert rules for time series metrics/PutResourceMetricRule.md)|Creates a performance metric alert rule for a resource.|
|[DeleteMetricRules](intl.en-US/API Reference/Alert rules for time series metrics/DeleteMetricRules.md)|Deletes one or more alert rules.|
|[DescribeMetricRuleCount](intl.en-US/API Reference/Alert rules for time series metrics/DescribeMetricRuleCount.md)|Queries the numbers of alert rules by status.|
|[DisableActiveMetricRule](intl.en-US/API Reference/Alert rules for time series metrics/DisableActiveMetricRule.md)|Disables one-click alert.|
|[EnableMetricRules](intl.en-US/API Reference/Alert rules for time series metrics/EnableMetricRules.md)|Enables one or more alert rules.|
|[DescribeMetricRuleList](intl.en-US/API Reference/Alert rules for time series metrics/DescribeMetricRuleList.md)|Queries alert rules.|
|[DisableMetricRules](intl.en-US/API Reference/Alert rules for time series metrics/DisableMetricRules.md)|Disables one or more alert rules.|
|[CreateGroupMetricRules](intl.en-US/API Reference/Alert rules for time series metrics/CreateGroupMetricRules.md)|Creates one or more alert rules for an application group.|
|[DescribeAlertHistoryList](intl.en-US/API Reference/Alert rules for time series metrics/DescribeAlertHistoryList.md)|Queries historical alerts.|
|[PutGroupMetricRule](intl.en-US/API Reference/Alert rules for time series metrics/PutGroupMetricRule.md)|Creates or modifies an alert rule for an application group.|
|[DescribeAlertingMetricRuleResources](intl.en-US/API Reference/Alert rules for time series metrics/DescribeAlertingMetricRuleResources.md)|Queries the resources with active alerts triggered based on an alert rule.|
|[PutMetricRuleTargets](intl.en-US/API Reference/Alert rules for time series metrics/PutMetricRuleTargets.md)|Adds or modifies targets of an alert rule.|
|[DescribeMetricRuleTargets](intl.en-US/API Reference/Alert rules for time series metrics/DescribeMetricRuleTargets.md)|Queries targets of an alert rule.|
|[DeleteMetricRuleTargets](intl.en-US/API Reference/Alert rules for time series metrics/DeleteMetricRuleTargets.md)|Deletes targets of an alert rule.|

## Host monitoring {#section_rxw_cnz_aui .section}

|Operation|Description|
|---------|-----------|
|[DeleteMonitoringAgentProcess](intl.en-US/API Reference/Host monitoring/DeleteMonitoringAgentProcess.md)|Disables monitoring on a process.|
|[DescribeMonitoringAgentStatuses](intl.en-US/API Reference/Host monitoring/DescribeMonitoringAgentStatuses.md)|Queries the status of the CloudMonitor agent.|
|[DescribeMonitoringAgentProcesses](intl.en-US/API Reference/Host monitoring/DescribeMonitoringAgentProcesses.md)|Queries monitored processes.|
|[DescribeMonitoringAgentAccessKey](intl.en-US/API Reference/Host monitoring/DescribeMonitoringAgentAccessKey.md)|Queries the AccessKey ID and AccessKey Secret required for installing the CloudMonitor agent on a non-Alibaba Cloud ECS host.|
|[UninstallMonitoringAgent](intl.en-US/API Reference/Host monitoring/UninstallMonitoringAgent.md)|Uninstalls the CloudMonitor agent on a non-Alibaba Cloud ECS host.|
|[InstallMonitoringAgent](intl.en-US/API Reference/Host monitoring/InstallMonitoringAgent.md)|Installs the CloudMonitor agent on one or more specified ECS hosts. This operation is not applicable to non-Alibaba Cloud ECS hosts.|
|[DescribeMonitoringAgentHosts](intl.en-US/API Reference/Host monitoring/DescribeMonitoringAgentHosts.md)|Queries the hosts where the CloudMonitor agent is installed.|
|[DescribeMonitoringAgentConfig](intl.en-US/API Reference/Host monitoring/DescribeMonitoringAgentConfig.md)|Queries configurations of the CloudMonitor agent.|
|[CreateMonitorAgentProcess](intl.en-US/API Reference/Host monitoring/CreateMonitorAgentProcess.md)|Enables monitoring on a process.|

## Application group {#section_lvo_iyx_rfh .section}

|Operation|Description|
|---------|-----------|
|[CreateMonitorGroupNotifyPolicy](intl.en-US/API Reference/Application group/CreateMonitorGroupNotifyPolicy.md)|Creates an alert notification pause policy for an application group.|
|[DeleteMonitorGroupNotifyPolicy](intl.en-US/API Reference/Application group/DeleteMonitorGroupNotifyPolicy.md)|Deletes an alert notification pause policy for an application group.|
|[DescribeMonitorGroupNotifyPolicyList](intl.en-US/API Reference/Application group/DescribeMonitorGroupNotifyPolicyList.md)|Queries alert notification pause policies of an application group.|
|[DeleteMonitorGroupInstances](intl.en-US/API Reference/Application group/DeleteMonitorGroupInstances.md)|Deletes resource instances from an application group.|
|[PutMonitorGroupDynamicRule](intl.en-US/API Reference/Application group/PutMonitorGroupDynamicRule.md)|Creates or modifies dynamic rules of an application group. Resources that meet the rules are automatically added to the application group.|
|[DeleteMonitorGroupDynamicRule](intl.en-US/API Reference/Application group/DeleteMonitorGroupDynamicRule.md)|Deletes dynamic rules of an application group.|
|[ModifyMonitorGroupInstances](intl.en-US/API Reference/Application group/ModifyMonitorGroupInstances.md)|Modifies resources in an application group.|
|[DescribeMonitorGroupDynamicRules](intl.en-US/API Reference/Application group/DescribeMonitorGroupDynamicRules.md)|Queries dynamic rules of an application group.|
|[DescribeMonitorGroupInstanceAttribute](intl.en-US/API Reference/Application group/DescribeMonitorGroupInstanceAttribute.md)|Queries details about resource instances of an application group.|
|[DescribeMonitorGroupCategories](intl.en-US/API Reference/Application group/DescribeMonitorGroupCategories.md)|Queries service resources in an application group and the number of instances that belong to each service in the application group.|
|[CreateMonitorGroup](intl.en-US/API Reference/Application group/CreateMonitorGroup.md)|Creates an application group.|
|[CreateMonitorGroupInstances](intl.en-US/API Reference/Application group/CreateMonitorGroupInstances.md)|Adds resources to an application group.|
|[DescribeMonitorGroups](intl.en-US/API Reference/Application group/DescribeMonitorGroups.md)|Queries application groups.|
|[ModifyMonitorGroup](intl.en-US/API Reference/Application group/ModifyMonitorGroup.md)|Modifies an application group.|
|[DescribeMonitorGroupInstances](intl.en-US/API Reference/Application group/DescribeMonitorGroupInstances.md)|Queries the resources contained in an application group.|
|[DeleteMonitorGroup](intl.en-US/API Reference/Application group/DeleteMonitorGroup.md)|Deletes an application group.|

## Availability monitoring {#section_pjs_w3k_zpf .section}

|Operation|Description|
|---------|-----------|
|[CreateHostAvailability](intl.en-US/API Reference/Availability monitoring/CreateHostAvailability.md)|Creates an availability monitoring task.|
|[DeleteHostAvailability](intl.en-US/API Reference/Availability monitoring/DeleteHostAvailability.md)|Deletes an availability monitoring task.|
|[ModifyHostAvailability](intl.en-US/API Reference/Availability monitoring/ModifyHostAvailability.md)|Modifies an availability monitoring task.|
|[EnableHostAvailability](intl.en-US/API Reference/Availability monitoring/EnableHostAvailability.md)|Enables availability monitoring.|
|[DescribeHostAvailabilityList](intl.en-US/API Reference/Availability monitoring/DescribeHostAvailabilityList.md)|Queries availability monitoring tasks.|
|[DescribeUnhealthyHostAvailability](intl.en-US/API Reference/Availability monitoring/DescribeUnhealthyHostAvailability.md)|Queries unhealthy servers.|
|[DisableHostAvailability](intl.en-US/API Reference/Availability monitoring/DisableHostAvailability.md)|Disables an availability monitoring task.|

## Global configurations {#section_ijd_wcz_amy .section}

|Operation|Description|
|---------|-----------|
|[DescribeMonitoringConfig](intl.en-US/API Reference/Global configurations/DescribeMonitoringConfig.md)|Queries global configurations of the CloudMonitor agent. For example, you can query whether automatic agent installation or one-click alert is enabled.|
|[PutMonitoringConfig](intl.en-US/API Reference/Global configurations/PutMonitoringConfig.md)|Makes global configurations for the CloudMonitor agent. For example, you can enable automatic agent installation or one-click alert.|

## Event monitoring data of cloud services {#section_tbi_4ux_vao .section}

|Operation|Description|
|---------|-----------|
|[DescribeSystemEventHistogram](intl.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventHistogram.md)|Queries the bar chart of the numbers of system events reported in different periods.|
|[SendDryRunSystemEvent](intl.en-US/API Reference/Event monitoring data of cloud services/SendDryRunSystemEvent.md)|Triggers a system event for debugging. This event is used to test whether the trigger logic of the event meets expectations.|
|[DescribeSystemEventMetaList](intl.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventMetaList.md)|Queries meta information of system events.|
|[DescribeSystemEventCount](intl.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventCount.md)|Queries the number of events related to a service that occurred in a specified period.|
|[DescribeSystemEventAttribute](intl.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventAttribute.md)|Queries detailed information of system events.|

## Alert templates for time series metrics {#section_dca_9lu_k9x .section}

|Operation|Description|
|---------|-----------|
|[ApplyMetricRuleTemplate](intl.en-US/API Reference/Alert templates for time series metrics/ApplyMetricRuleTemplate.md)|Applies an alert template to an application group to generate an alert rule.|
|[DescribeMetricRuleTemplateAttribute](intl.en-US/API Reference/Alert templates for time series metrics/DescribeMetricRuleTemplateAttribute.md)|Queries detailed information of an alert template.|
|[ModifyMetricRuleTemplate](intl.en-US/API Reference/Alert templates for time series metrics/ModifyMetricRuleTemplate.md)|Modifies an alert template.|
|[DescribeMetricRuleTemplateList](intl.en-US/API Reference/Alert templates for time series metrics/DescribeMetricRuleTemplateList.md)|Queries alert templates.|
|[CreateMetricRuleTemplate](intl.en-US/API Reference/Alert templates for time series metrics/CreateMetricRuleTemplate.md)|Creates an alert template.|
|[DeleteMetricRuleTemplate](intl.en-US/API Reference/Alert templates for time series metrics/DeleteMetricRuleTemplate.md)|Deletes an alert template.|

## Event alert rule {#section_f2n_dtk_zvl .section}

|Operation|Description|
|---------|-----------|
|[DescribeEventRuleAttribute](intl.en-US/API Reference/Event alert rules/DescribeEventRuleAttribute.md)|Queries detailed information of an event alert rule.|
|[PutEventRuleTargets](intl.en-US/API Reference/Event alert rules/PutEventRuleTargets.md)|Adds or modifies targets of an event alert rule.|
|[DeleteEventRuleTargets](intl.en-US/API Reference/Event alert rules/DeleteEventRuleTargets.md)|Deletes targets of an event alert rule.|
|[EnableEventRules](intl.en-US/API Reference/Event alert rules/EnableEventRules.md)|Enables one or more event alert rules.|
|[DescribeEventRuleList](intl.en-US/API Reference/Event alert rules/DescribeEventRuleList.md)|Queries event alert rules.|
|[DeleteEventRules](intl.en-US/API Reference/Event alert rules/DeleteEventRules.md)|Deletes event alert rules.|
|[DisableEventRules](intl.en-US/API Reference/Event alert rules/DisableEventRules.md)|Disables one or more event alert rules.|
|[PutEventRule](intl.en-US/API Reference/Event alert rules/PutEventRule.md)|Creates or modifies an event alert rule.|
|[DescribeEventRuleTargetList](intl.en-US/API Reference/Event alert rules/DescribeEventRuleTargetList.md)|Queries targets of an event alert rule.|

## Custom monitoring {#section_aqo_fnf_v5u .section}

|Operation|Description|
|---------|-----------|
|[PutCustomMetric](intl.en-US/API Reference/Custom monitoring/PutCustomMetric.md)|Reports custom monitoring data.|
|[DescribeCustomMetricList](intl.en-US/API Reference/Custom monitoring/DescribeCustomMetricList.md)|Queries the reported custom monitoring data.|
|[DeleteCustomMetric](intl.en-US/API Reference/Custom monitoring/DeleteCustomMetric.md)|Deletes custom monitoring data.|

## Custom event {#section_cd6_6tp_fjr .section}

|Operation|Description|
|---------|-----------|
|[DescribeCustomEventCount](intl.en-US/API Reference/Custom event/DescribeCustomEventCount.md)|Queries the statistics of custom events. The statistics contain the numbers of custom events for each service.|
|[DescribeCustomEventAttribute](intl.en-US/API Reference/Custom event/DescribeCustomEventAttribute.md)|Queries detailed information of one or more custom events.|
|[DescribeCustomEventHistogram](intl.en-US/API Reference/Custom event/DescribeCustomEventHistogram.md)|Queries the distribution chart of the numbers of the reported custom events in different periods.|
|[PutCustomEvent](intl.en-US/API Reference/Custom event/PutCustomEvent.md)|Reports the monitoring data for one or more custom events.|

## Site monitoring {#section_syl_xni_qf9 .section}

|Operation|Description|
|---------|-----------|
|[DisableSiteMonitors](intl.en-US/API Reference/Site monitoring/DisableSiteMonitors.md)|Disables one or more site monitoring tasks.|
|[DescribeSiteMonitorQuota](intl.en-US/API Reference/Site monitoring/DescribeSiteMonitorQuota.md)|Queries the quota and version of site monitoring.|
|[DescribeSiteMonitorAttribute](intl.en-US/API Reference/Site monitoring/DescribeSiteMonitorAttribute.md)|Queries detailed information of a site monitoring task.|
|[DeleteSiteMonitors](intl.en-US/API Reference/Site monitoring/DeleteSiteMonitors.md)|Deletes one or more site monitoring tasks.|
|[DescribeSiteMonitorISPCityList](intl.en-US/API Reference/Site monitoring/DescribeSiteMonitorISPCityList.md)|Queries the detection points that are available for creating site monitoring tasks.|
|[DescribeSiteMonitorData](intl.en-US/API Reference/Site monitoring/DescribeSiteMonitorData.md)|Queries detailed monitoring data of a site monitoring task.|
|[DescribeSiteMonitorStatistics](intl.en-US/API Reference/Site monitoring/DescribeSiteMonitorStatistics.md)|Queries the statistics of a specified site monitoring task in a specified period.|
|[CreateSiteMonitor](intl.en-US/API Reference/Site monitoring/CreateSiteMonitor.md)|Creates a site monitoring task.|
|[ModifySiteMonitor](intl.en-US/API Reference/Site monitoring/ModifySiteMonitor.md)|Modifies a site monitoring task.|
|[EnableSiteMonitors](intl.en-US/API Reference/Site monitoring/EnableSiteMonitors.md)|Enables one or more site monitoring tasks.|
|[DescribeSiteMonitorList](intl.en-US/API Reference/Site monitoring/DescribeSiteMonitorList.md)|Queries site monitoring tasks.|

