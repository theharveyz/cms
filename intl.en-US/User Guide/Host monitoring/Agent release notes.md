# Agent release notes {#concept_nbn_5hv_vdb .concept}

## 1.2.11 {#section_dn3_xx2_xdb .section}

Feature optimization and bug fixes. If you are using the local health check function, you will need to upgrade to this agent version.

New feature

-   Added local and remote protocol detection with support for Telnet and HTTP protocols

Feature optimization and bug fixes

-   Fixed the privilege escalation loophole that may have occurred when the tmp directory was used as the temporary download directory of the installation script.
-   Fixed the bug of submitting identical device data when the same disk is attached multiple times.
-   Fixed the bug that some processes cannot obtain the path and name is fixed.
-   Optimized the file download method to prevent monitoring process blocking that may have resulted from the downloading process.

## 1.1.64 {#section_gn3_xx2_xdb .section}

Feature optimization and bug fixes. We recommend those using agent versions after CentOS 7.2 to upgrade to this version.

-   Optimized memory usage calculation accuracy by adjusting the memory usage collection logic with MemAvailable filed used for available memory estimation for agent versions after CentOS 7.2.

## 1.1.63 {#section_in3_xx2_xdb .section}

Feature optimization and bug fixes

-   Adjusted the default wrapper log to the info level.
-   Optimized fault detection with added error-level log information added.
-   Fixed the risk of memory leakage that may have resulted from logs at the debug level.

## 1.1.62 {#section_kn3_xx2_xdb .section}

Feature optimization and bug fixes

-   Optimized the HTTP Proxy selection logic to improve the agent installation success rate.
-   Added key logs for improved fault detection.

## 1.1.61 {#section_mn3_xx2_xdb .section}

Feature optimization and bug fixes

-   Fixed the incorrect collection of topN processes bug that resulted from the abnormal collection of process user names by some systems.

## 1.1.59 {#section_on3_xx2_xdb .section}

Feature optimization and bug fixes

-   Optimized the process count collection method to improve performance.
-   Adjusted process monitoring so that two CloudMonitor agent processes are excluded from process count collection.

