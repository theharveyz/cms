# Agent release notes {#concept_nbn_5hv_vdb .concept}

This topic describes the different versions of the host monitoring agent.

## 2.1.55 {#section_lwj_fbf_vgb .section}

Release date: January 24, 2019

**Feature optimization and bug fixes:**

Fixed the bug that prevented the agent from collecting monitoring data after an ECS instance restarts.

**Upgrade recommendations:**

If your host runs a Go language agent of a version earlier than 2.1.55, we recommend that you upgrade the agent to this version.

## 2.1.54 {#section_hlz_fbf_vgb .section}

Release date: January 3, 2019

**Feature optimization and bug fixes:**

Fixed the bug that prevented the agent from collecting monitoring data from graphics processing unit \(GPU\) servers running a Windows operating system.

**Upgrade recommendations:**

If your host runs a Go language agent of a version earlier than 2.1.54 on a Windows operating system, we recommend that you upgrade the agent to this version.

## 2.1.53 {#section_xzz_fbf_vgb .section}

Release date: December 25, 2018

**Feature optimization and bug fixes:**

Fixed the bug that prevented the agent from collecting ECS monitoring data from classic networks.

**Upgrade recommendations:**

If your host runs a Go language agent of a version earlier than 2.1.53 in a classic network, we recommend that you upgrade the agent to this version.

## 2.1.51 {#section_mh1_gbf_vgb .section}

Release date: December 4, 2018

**Feature optimization and bug fixes:**

-   Fixed the bug that displayed the disk monitoring mount point as a hexadecimal string.
-   Pre-check: Check the operating system version, system memory, remaining disk capacity, and connectivity to the CloudMonitor server before installing the agent, to determine whether the agent can be successfully installed.

**Upgrade recommendations:**

If your host runs a Go language agent of a version earlier than 2.1.50, we recommend that you upgrade the agent to this version.

## 2.1.50 {#section_m41_gbf_vgb .section}

Release date: November 29, 2018

**New features:**

The Go programming language version is officially released. Compared with the Java version, the Go programming language version significantly reduces host performance consumption and provides more stable monitoring services. For more information, see [Introduction to the CloudMonitor GoLang agent](reseller.en-US/User Guide/Host monitoring/Introduction to the CloudMonitor GoLang agent.md#).

**Upgrade recommendations:**

If your host runs a Java agent of 1.X.X version, we recommend that you upgrade the agent to this version. On the Host Monitoring page, select a host from the instance list, and click **Install Plugins**.

## 1.2.11 {#section_dn3_xx2_xdb .section}

**New features:**

Protocol-dependent local and remote detection through Telnet and HTTP

**Feature optimization and bug fixes:**

-   Fixed the bug that may cause the privilege escalation loophole to occur when the tmp directory is used as the temporary download directory of the installation script.
-   Fixed the bug that submitted identical device data when the same disk is attached more than once.
-   Fixed the bug that prevented certain processes from obtaining the path and name.
-   Optimized the file download method to prevent the download process from blocking the monitoring process.

**Upgrade recommendations**

When using the local health check function, upgrade the agent to this version.

## 1.1.64 {#section_gn3_xx2_xdb .section}

**Feature optimization and bug fixes:**

The memory usage collection logic is adjusted. For versions later than CentOS 7.2, the `/proc/meminfo MemAvailable` field is used for available memory estimation to improve the accuracy of memory usage calculation.

**Upgrade recommendations:**

If your host runs CentOS 7.2 or later, we recommend that you upgrade the agent to this version.

## 1.1.63 {#section_in3_xx2_xdb .section}

**Feature optimization and bug fixes:**

-   Changed the default wrapper log to the info level.
-   Added log information of the error level for easy failure location.
-   Fixed the bug that may cause memory leakage for logs at the debug level.

## 1.1.62 {#section_kn3_xx2_xdb .section}

**Feature optimization and bug fixes:**

-   Optimized the HTTP Proxy selection logic to improve the agent installation success rate.
-   Added key logs for easy failure location.

## 1.1.61 {#section_mn3_xx2_xdb .section}

**Feature optimization and bug fixes:**

Fixed the bug that may cause exceptions to occur when certain systems collect process user names, thus causing incorrect topN process collection.

## 1.1.59 {#section_on3_xx2_xdb .section}

**Feature optimization and bug fixes:**

-   Optimized the process count collection method to improve performance.
-   Adjusted process monitoring so that two CloudMonitor agent processes are excluded from process count collection.

