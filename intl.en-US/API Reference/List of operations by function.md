# List of operations by function {#doc_14254 .concept}

This topic lists all the CloudMonitor operations that you can call.

## Time series data of cloud services {#section_h7p_phf_owp .section}

|Operation|Description|
|---------|-----------|
|[DescribeProjectMeta](reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeProjectMeta.md)|Queries information about monitored services in CloudMonitor.|
|[DescribeMetricLast](reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricLast.md)|Queries the latest monitoring data of a monitored object.|
|[DescribeMetricMetaList](reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricMetaList.md)|Queries the descriptions of time series available in CloudMonitor.|
|[DescribeMetricList](reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricList.md)|Queries the time series of cloud services in a specified period.|
|[DescribeMetricData](reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricData.md)|Queries the time series details of cloud services in a specified period.|
|[DescribeMetricTop](reseller.en-US/API Reference/Monitoring data on time series metrics of cloud services/DescribeMetricTop.md)|Queries the time series data of cloud services sorted by specified fields in a specified period.|

## Alert contact groups {#section_t4w_dld_oil .section}

|Operation|Description|
|---------|-----------|
|[DescribeContactListByContactGroup](reseller.en-US/API Reference/Alert contact group/DescribeContactListByContactGroup.md)|Queries the list of alert contacts in an alert contact group.|
|[DeleteContactGroup](reseller.en-US/API Reference/Alert contact group/DeleteContactGroup.md)|Deletes an alert contact group.|
|[DescribeContactGroupList](reseller.en-US/API Reference/Alert contact group/DescribeContactGroupList.md)|Queries the list of alert contact groups.|
|[PutContact](reseller.en-US/API Reference/Alert contact group/PutContact.md)|Creates or modifies an alert contact.|
|[DeleteContact](reseller.en-US/API Reference/Alert contact group/DeleteContact.md)|Deletes an alert contact.|
|[DescribeContactList](reseller.en-US/API Reference/Alert contact group/DescribeContactList.md)|Queries the list of alert contacts.|
|[PutContactGroup](reseller.en-US/API Reference/Alert contact group/PutContactGroup.md)|Creates or modifies an alert contact group.|

## Alert rules for time series {#section_ve5_ueo_ixs .section}

|Operation|Description|
|---------|-----------|
|[ListContactGroup](reseller.en-US/API Reference/Alert rules for time series metrics/ListContactGroup.md)|Queries the contact group associated with an alert rule under an Alibaba Cloud account.|
|[DescribeProductsOfActiveMetricRule](reseller.en-US/API Reference/Alert rules for time series metrics/DescribeProductsOfActiveMetricRule.md)|Queries the list of services for which one-click alert is enabled.|
|[EnableActiveMetricRule](reseller.en-US/API Reference/Alert rules for time series metrics/EnableActiveMetricRule.md)|Enables one-click alert for a service.|
|[DescribeActiveMetricRuleList](reseller.en-US/API Reference/Alert rules for time series metrics/DescribeActiveMetricRuleList.md)|Queries the details for the list of one-click alert rules.|
|[PutResourceMetricRule](reseller.en-US/API Reference/Alert rules for time series metrics/PutResourceMetricRule.md)|Configures a performance metric alert rule for a resource.|
|[DeleteMetricRules](reseller.en-US/API Reference/Alert rules for time series metrics/DeleteMetricRules.md)|Deletes one or more alert rules.|
|[DescribeMetricRuleCount](reseller.en-US/API Reference/Alert rules for time series metrics/DescribeMetricRuleCount.md)|Queries the number of alert rules by status.|
|[DisableActiveMetricRule](reseller.en-US/API Reference/Alert rules for time series metrics/DisableActiveMetricRule.md)|Disables one-click alert.|
|[EnableMetricRules](reseller.en-US/API Reference/Alert rules for time series metrics/EnableMetricRules.md)|Enables one or more alert rules.|
|[DescribeMetricRuleList](reseller.en-US/API Reference/Alert rules for time series metrics/DescribeMetricRuleList.md)|Queries the list of alert rules.|
|[DisableMetricRules](reseller.en-US/API Reference/Alert rules for time series metrics/DisableMetricRules.md)|Disables one or more alert rules.|
|[CreateGroupMetricRules](reseller.en-US/API Reference/Alert rules for time series metrics/CreateGroupMetricRules.md)|Creates multiple metric alert rules for an application group.|
|[DescribeAlertHistoryList](reseller.en-US/API Reference/Alert rules for time series metrics/DescribeAlertHistoryList.md)|Queries the list of historical alerts.|
|[PutGroupMetricRule](reseller.en-US/API Reference/Alert rules for time series metrics/PutGroupMetricRule.md)|Creates or modifies a group alert rule.|
|[DescribeAlertingMetricRuleResources](reseller.en-US/API Reference/Alert rules for time series metrics/DescribeAlertingMetricRuleResources.md)|Queries the resources with active alerts triggered based on an alert rule.|
|[PutMetricRuleTargets](reseller.en-US/API Reference/Alert rules for time series metrics/PutMetricRuleTargets.md)|Adds or modifies targets of an alert rule.|
|[DescribeMetricRuleTargets](reseller.en-US/API Reference/Alert rules for time series metrics/DescribeMetricRuleTargets.md)|Queries targets associated with an alert rule.|
|[DeleteMetricRuleTargets](reseller.en-US/API Reference/Alert rules for time series metrics/DeleteMetricRuleTargets.md)|Deletes targets of an alert rule.|
|[CreateMetricRuleResources](reseller.en-US/API Reference/Alert rules for time series metrics/CreateMetricRuleResources.md)|Creates a resource associated with an alert rule.|
|[DeleteMetricRuleResources](reseller.en-US/API Reference/Alert rules for time series metrics/DeleteMetricRuleResources.md)|Deletes resources associated with an alert rule.|

## Host monitoring {#section_yff_b2e_ovz .section}

|Operation|Description|
|---------|-----------|
|[DeleteMonitoringAgentProcess](reseller.en-US/API Reference/Host monitoring/DeleteMonitoringAgentProcess.md)|Disables monitoring on a process.|
|[DescribeMonitoringAgentStatuses](reseller.en-US/API Reference/Host monitoring/DescribeMonitoringAgentStatuses.md)|Queries the status of the CloudMonitor agent.|
|[DescribeMonitoringAgentProcesses](reseller.en-US/API Reference/Host monitoring/DescribeMonitoringAgentProcesses.md)|Queries the process monitoring list.|
|[DescribeMonitoringAgentAccessKey](reseller.en-US/API Reference/Host monitoring/DescribeMonitoringAgentAccessKey.md)|Queries the AccessKey ID and AccessKey Secret required to install the CloudMonitor agent on a host other than Alibaba Cloud ECS instances.|
|[UninstallMonitoringAgent](reseller.en-US/API Reference/Host monitoring/UninstallMonitoringAgent.md)|Uninstalls the CloudMonitor agent from a host other than Alibaba Cloud ECS instances.|
|[InstallMonitoringAgent](reseller.en-US/API Reference/Host monitoring/InstallMonitoringAgent.md)|Installs the CloudMonitor agent for a specified ECS instance. This operation is only applicable to Alibaba Cloud ECS instances.|
|[DescribeMonitoringAgentHosts](reseller.en-US/API Reference/Host monitoring/DescribeMonitoringAgentHosts.md)|Queries the list of hosts where the CloudMonitor agent is installed.|
|[DescribeMonitoringAgentConfig](reseller.en-US/API Reference/Host monitoring/DescribeMonitoringAgentConfig.md)|Queries the configuration of the CloudMonitor agent.|
|[CreateMonitorAgentProcess](reseller.en-US/API Reference/Host monitoring/CreateMonitorAgentProcess.md)|Enables monitoring on a process.|

## Application group {#section_pce_irz_urq .section}

|Operation|Description|
|---------|-----------|
|[CreateMonitorGroupNotifyPolicy](reseller.en-US/API Reference/Application group/CreateMonitorGroupNotifyPolicy.md)|Creates a pause notification policy for an application group.|
|[DeleteMonitorGroupNotifyPolicy](reseller.en-US/API Reference/Application group/DeleteMonitorGroupNotifyPolicy.md)|Deletes a pause notification policy for an application group.|
|[DescribeMonitorGroupNotifyPolicyList](reseller.en-US/API Reference/Application group/DescribeMonitorGroupNotifyPolicyList.md)|Queries the list of pause notification policies for an application group.|
|[DeleteMonitorGroupInstances](reseller.en-US/API Reference/Application group/DeleteMonitorGroupInstances.md)|Deletes resource instances from an application group.|
|[PutMonitorGroupDynamicRule](reseller.en-US/API Reference/Application group/PutMonitorGroupDynamicRule.md)|Creates or modifies the dynamic rules of an application group. Resources that meet the rules are automatically added to the application group.|
|[DeleteMonitorGroupDynamicRule](reseller.en-US/API Reference/Application group/DeleteMonitorGroupDynamicRule.md)|Deletes the dynamic rules of an application group.|
|[ModifyMonitorGroupInstances](reseller.en-US/API Reference/Application group/ModifyMonitorGroupInstances.md)|Modifies resources in an application group.|
|[DescribeMonitorGroupDynamicRules](reseller.en-US/API Reference/Application group/DescribeMonitorGroupDynamicRules.md)|Queries the list of dynamic rules for an application group.|
|[DescribeMonitorGroupInstanceAttribute](reseller.en-US/API Reference/Application group/DescribeMonitorGroupInstanceAttribute.md)|Queries the resource instance details of an application group.|
|[DescribeMonitorGroupCategories](reseller.en-US/API Reference/Application group/DescribeMonitorGroupCategories.md)|Queries the list of service resources in an application group, and the number of instances that belong to each service in the application group.|
|[CreateMonitorGroup](reseller.en-US/API Reference/Application group/CreateMonitorGroup.md)|Creates an application group.|
|[CreateMonitorGroupInstances](reseller.en-US/API Reference/Application group/CreateMonitorGroupInstances.md)|Adds resources to an application group.|
|[DescribeMonitorGroups](reseller.en-US/API Reference/Application group/DescribeMonitorGroups.md)|Queries the list of application groups.|
|[ModifyMonitorGroup](reseller.en-US/API Reference/Application group/ModifyMonitorGroup.md)|Modifies an application group.|
|[DescribeMonitorGroupInstances](reseller.en-US/API Reference/Application group/DescribeMonitorGroupInstances.md)|Queries the list of resources contained in a specified application group.|
|[DeleteMonitorGroup](reseller.en-US/API Reference/Application group/DeleteMonitorGroup.md)|Deletes an application group.|

## Availability monitoring {#section_hl2_p6d_kgn .section}

|Operation|Description|
|---------|-----------|
|[CreateHostAvailability](reseller.en-US/API Reference/Availability monitoring/CreateHostAvailability.md)|Creates an availability monitoring task.|
|[DeleteHostAvailability](reseller.en-US/API Reference/Availability monitoring/DeleteHostAvailability.md)|Deletes an availability monitoring task.|
|[ModifyHostAvailability](reseller.en-US/API Reference/Availability monitoring/ModifyHostAvailability.md)|Modifies an availability monitoring task.|
|[EnableHostAvailability](reseller.en-US/API Reference/Availability monitoring/EnableHostAvailability.md)|Enables an availability monitoring task.|
|[DescribeHostAvailabilityList](reseller.en-US/API Reference/Availability monitoring/DescribeHostAvailabilityList.md)|Queries the list of availability monitoring tasks.|
|[DescribeUnhealthyHostAvailability](reseller.en-US/API Reference/Availability monitoring/DescribeUnhealthyHostAvailability.md)|Queries the list of unhealthy hosts.|
|[DisableHostAvailability](reseller.en-US/API Reference/Availability monitoring/DisableHostAvailability.md)|Disables an availability monitoring task.|

## Global configurations {#section_btp_fdm_f2t .section}

|Operation|Description|
|---------|-----------|
|[DescribeMonitoringConfig](reseller.en-US/API Reference/Global configurations/DescribeMonitoringConfig.md)|Queries the global configurations of the CloudMonitor agent. For example, you can query whether automatic agent installation or one-click alert is enabled.|
|[PutMonitoringConfig](reseller.en-US/API Reference/Global configurations/PutMonitoringConfig.md)|Sets global configurations for the CloudMonitor agent. For example, you can enable automatic agent installation or one-click alert.|

## Event monitoring data of cloud services {#section_kbv_jho_3ox .section}

|Operation|Description|
|---------|-----------|
|[DescribeSystemEventHistogram](reseller.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventHistogram.md)|Queries the bar chart that indicates the number of system events reported in different periods.|
|[SendDryRunSystemEvent](reseller.en-US/API Reference/Event monitoring data of cloud services/SendDryRunSystemEvent.md)|Triggers a system event for debugging. This event is used to test whether the trigger logic of the event meets expectations.|
|[DescribeSystemEventMetaList](reseller.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventMetaList.md)|Queries the meta information of system events.|
|[DescribeSystemEventCount](reseller.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventCount.md)|Queries the number of events related to a service that occurred in a specified period of time.|
|[DescribeSystemEventAttribute](reseller.en-US/API Reference/Event monitoring data of cloud services/DescribeSystemEventAttribute.md)|Queries system event details.|

## Alert templates for time series {#section_cfm_efy_m9p .section}

|Operation|Description|
|---------|-----------|
|[ApplyMetricRuleTemplate](reseller.en-US/API Reference/Alert templates for time series metrics/ApplyMetricRuleTemplate.md)|Applies an alert rule template to an application group to generate an alert rule.|
|[DescribeMetricRuleTemplateAttribute](reseller.en-US/API Reference/Alert templates for time series metrics/DescribeMetricRuleTemplateAttribute.md)|Queries the details of an alert rule template.|
|[ModifyMetricRuleTemplate](reseller.en-US/API Reference/Alert templates for time series metrics/ModifyMetricRuleTemplate.md)|Modifies an alert rule template.|
|[DescribeMetricRuleTemplateList](reseller.en-US/API Reference/Alert templates for time series metrics/DescribeMetricRuleTemplateList.md)|Queries the list of alert rule templates.|
|[CreateMetricRuleTemplate](reseller.en-US/API Reference/Alert templates for time series metrics/CreateMetricRuleTemplate.md)|Creates an alert rule template.|
|[DeleteMetricRuleTemplate](reseller.en-US/API Reference/Alert templates for time series metrics/DeleteMetricRuleTemplate.md)|Deletes an alert rule template.|

## Event alert rules {#section_bko_avd_r8p .section}

|Operation|Description|
|---------|-----------|
|[DescribeEventRuleAttribute](reseller.en-US/API Reference/Event alert rules/DescribeEventRuleAttribute.md)|Queries the details of an alert rule.|
|[PutEventRuleTargets](reseller.en-US/API Reference/Event alert rules/PutEventRuleTargets.md)|Creates or modifies notification objects for an alert rule.|
|[DeleteEventRuleTargets](reseller.en-US/API Reference/Event alert rules/DeleteEventRuleTargets.md)|Deletes one or more notification objects of event alerts.|
|[EnableEventRules](reseller.en-US/API Reference/Event alert rules/EnableEventRules.md)|Enables one or more event alert rules.|
|[DescribeEventRuleList](reseller.en-US/API Reference/Event alert rules/DescribeEventRuleList.md)|Queries the list of event alerts.|
|[DeleteEventRules](reseller.en-US/API Reference/Event alert rules/DeleteEventRules.md)|Deletes one or more event alert rules.|
|[DisableEventRules](reseller.en-US/API Reference/Event alert rules/DisableEventRules.md)|Disables one or more event alert rules.|
|[PutEventRule](reseller.en-US/API Reference/Event alert rules/PutEventRule.md)|Creates or modifies an event alert rule.|
|[DescribeEventRuleTargetList](reseller.en-US/API Reference/Event alert rules/DescribeEventRuleTargetList.md)|Queries the notification objects of an event alert rule.|

## Custom monitoring {#section_25o_fig_udd .section}

|Operation|Description|
|---------|-----------|
|[PutCustomMetric](reseller.en-US/API Reference/Custom monitoring/PutCustomMetric.md)|Queries the monitoring data of one or more custom metrics.|
|[DescribeCustomMetricList](reseller.en-US/API Reference/Custom monitoring/DescribeCustomMetricList.md)|Queries the monitoring data of a custom metric.|
|[DeleteCustomMetric](reseller.en-US/API Reference/Custom monitoring/DeleteCustomMetric.md)|Deletes the monitoring data of a custom metric.|

## Custom event {#section_7ky_rgi_k8d .section}

|Operation|Description|
|---------|-----------|
|[DescribeCustomEventCount](reseller.en-US/API Reference/Custom event/DescribeCustomEventCount.md)|Queries the number of custom events.|
|[DescribeCustomEventAttribute](reseller.en-US/API Reference/Custom event/DescribeCustomEventAttribute.md)|Queries the details of a custom event.|
|[DescribeCustomEventHistogram](reseller.en-US/API Reference/Custom event/DescribeCustomEventHistogram.md)|Queries the distribution chart of the number of reported custom events in different periods.|
|[PutCustomEvent](reseller.en-US/API Reference/Custom event/PutCustomEvent.md)|Reports the monitoring data for one or more custom events.|

## Site monitoring {#section_suw_wlh_dqf .section}

|Operation|Description|
|---------|-----------|
|[DisableSiteMonitors](reseller.en-US/API Reference/Site monitoring/DisableSiteMonitors.md)|Disables one or more site monitoring tasks.|
|[DescribeSiteMonitorQuota](reseller.en-US/API Reference/Site monitoring/DescribeSiteMonitorQuota.md)|Queries the quota and version of site monitoring.|
|[DescribeSiteMonitorAttribute](reseller.en-US/API Reference/Site monitoring/DescribeSiteMonitorAttribute.md)|Queries site monitoring details.|
|[DeleteSiteMonitors](reseller.en-US/API Reference/Site monitoring/DeleteSiteMonitors.md)|Deletes a site monitoring task.|
|[DescribeSiteMonitorISPCityList](reseller.en-US/API Reference/Site monitoring/DescribeSiteMonitorISPCityList.md)|Queries the list of sites that can be used to create a task.|
|[DescribeSiteMonitorData](reseller.en-US/API Reference/Site monitoring/DescribeSiteMonitorData.md)|Queries the fine-grained monitoring data of a task.|
|[DescribeSiteMonitorStatistics](reseller.en-US/API Reference/Site monitoring/DescribeSiteMonitorStatistics.md)|Queries the average statistics of a specified task over a period of time.|
|[CreateSiteMonitor](reseller.en-US/API Reference/Site monitoring/CreateSiteMonitor.md)|Creates a site monitoring task.|
|[ModifySiteMonitor](reseller.en-US/API Reference/Site monitoring/ModifySiteMonitor.md)|Modifies a site monitoring task.|
|[EnableSiteMonitors](reseller.en-US/API Reference/Site monitoring/EnableSiteMonitors.md)|Enables one or more site monitoring tasks.|
|[DescribeSiteMonitorList](reseller.en-US/API Reference/Site monitoring/DescribeSiteMonitorList.md)|Queries the list of site monitoring tasks.|

