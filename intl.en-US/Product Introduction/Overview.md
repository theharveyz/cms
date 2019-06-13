# Overview {#concept_awy_bh4_tdb .concept}

CloudMonitor is a service provided by Alibaba cloud to monitor Alibaba Cloud resources and Internet applications.

CloudMonitor provides one-stop, ready-to-go, and enterprise-class monitoring solutions for cloud users. CloudMonitor is able to monitor IT facilities, external network quality, events, custom metrics, and service logs. CloudMonitor provides you with efficient, comprehensive, and cost-effective monitoring services. CloudMonitor utilizes cross-service and cross-region application group management models and alert templates. CloudMonitor allows you to build an efficient management system to monitor and send alert notification for dozens of cloud services and tens of thousands of instances. With CloudMonitor, you can build and customize a monitoring dashboard for your services. CloudMonitor helps you increase system service availability and reduce the O&M costs of IT systems.

CloudMonitor collects data on Alibaba Cloud resource metrics and custom metrics. CloudMonitor can be used to detect the availability of your service and allows you to configure alerts on specific metrics. CloudMonitor provides a real-time overview of cloud services, resource usage, and alerts. With this information, you can promptly react to exceptions and ensure the availability of your applications.

## Architecture {#section_zm2_cxf_xgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6120/15604102926442_en-US.png)

## Features {#section_vph_mxf_xgb .section}

CloudMonitor provides the following features:

-   **Dashboard**: allows you to view the monitoring data as needed. On a dashboard, you can view the monitoring data of multiple services and instances from a central location.
-   **Application group**: allows you to group regions and services together to manage their resources. With this feature, you can manage service-related resources such as servers, databases, Server Load Balancer \(SLB\) instances, and storage. You can manage alert rules and view the monitoring data related to each service to streamline O&M.
-   **Host monitoring**: installs plug-ins on servers to monitor and provide alert functions for over 30 metrics such as CPUs, memory, disks, and networks. You can configure alert rules based on instances, application groups, or resources. You can customize rules for different services based on different metrics. Currently, host monitoring is supported on both Linux and Windows.
-   **Custom monitoring**: allows you to monitor custom metrics that are of concern to your business requirements. The collected monitoring data is reported to CloudMonitor. CloudMonitor processes data and generates alerts based on processing results.
-   **Cloud service monitoring**: allows you to query the performance indicators of the purchased cloud service instances. This information helps you analyze the resource usage, collect statistics about the business trend, and identify and diagnose system faults in a timely manner.
-   **Event monitoring**: provides report, query, and alarm functions for events. Event monitoring reports exceptions and important changes in your business to CloudMonitor and sends alerts when exceptions occur.
-   **Alert service**: sends alerts when the metric values exceed the preconfigured thresholds. You can configure alert rules to specify how the alert system checks the monitoring data and when it sends alerts. By configuring alert rules on important metrics, you can receive notification immediately after any metric data exceptions occur. Then, you will be able to handle the exceptions in time.

