# 插件 Release Notes {#concept_nbn_5hv_vdb .concept}

## 1.2.11 {#section_dn3_xx2_xdb .section}

使用本地健康检查功能，需要将插件升级至此版本。

新功能

-   新增本地及远程协议探测功能，支持Telnet、HTTP协议探测。

已知问题的修复与优化

-   修复安装脚本的临时下载目录为tmp目录可能导致提权漏洞的问题。
-   修复同一个磁盘设备被挂多次，导致提交相同设备数据的问题。
-   修复部分进程无法获得path与name的问题。
-   优化文件下载方式，解决下载可能阻塞监控进程的问题。

## 1.1.64 {#section_gn3_xx2_xdb .section}

已知问题的修复与优化，建议CentOS7.2以上版本的用户升级插件至此版本。

-   调整内存使用率采集逻辑，centos7.2以上的版本使用`/proc/meminfo MemAvailable`字段作为可用内存估算依据，提升内存使用率计算准确性。

## 1.1.63 {#section_in3_xx2_xdb .section}

已知问题的修复与优化

-   调整默认wrapper log为info级别。
-   增加error级别日志信息，方便定位问题。
-   修复debug级别日志可能导致内存泄露风险的问题。

## 1.1.62 {#section_kn3_xx2_xdb .section}

已知问题的修复与优化

-   优化HTTP Proxy选择逻辑，提升插件安装成功率。
-   添加关键日志，更容易定位问题。

## 1.1.61 {#section_mn3_xx2_xdb .section}

已知问题的修复与优化

-   修复部分系统采集进程用户名时可能异常，导致topN进程采集不正确的问题。

## 1.1.59 {#section_on3_xx2_xdb .section}

已知问题的修复与优化

-   优化进程数采集方式，提升性能。
-   进程监控中进程数采集不再计算云监控插件自身的2个进程。

