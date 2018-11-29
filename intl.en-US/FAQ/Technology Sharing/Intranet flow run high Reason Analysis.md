# Intranet flow run high Reason Analysis {#concept_yhz_f5k_zdb .concept}

In the CloudMonitor, the intranet traffic runs high, as shown in the following figure:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6264/15434737674956_en-US.jpg)

Generally, the servers provide services to external parties over the Internet NIC. The intranet usage is usually low, unless when SLB is used \(SLB communicates with ECS and intranet\). The high intranet traffic is usually because other ECS servers are copying data to this server.

If it is not because of copying data, another common cause is virus attacks to the server, resulting in a large number of packet forwarding. In this case, if the operating system of the server is Linux, you can install NetHogs in the system to view the traffic of specific processes:

```
#yum install nethogs Install NetHogs
```

```
#nethogs eth0         View the specific traffic usage of the intranet NIC
```

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6264/15434737674957_en-US.jpg) 

With the help of NetHogs, you can see the specific intranet bandwidth usage and figure out which processes occupy the intranet bandwidth.

If you are using the system of Windows 2008 or later, you can go to the Resource Monitor to see the processes that occupy the bandwidth:

Right-click on the server's taskbar and select start Task Manager resource monitor network, you can see the specific processes that consume network traffic.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6264/15434737674959_en-US.jpg)

