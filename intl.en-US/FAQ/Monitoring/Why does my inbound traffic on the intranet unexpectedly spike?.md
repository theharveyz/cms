# Why does my inbound traffic on the intranet unexpectedly spike? {#concept_yhz_f5k_zdb .concept}

In the CloudMonitor console, you may see a sudden spike in inbound traffic on the intranet, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6264/15532456344956_en-US.jpg)

Generally, inbound traffic on the intranet tends to be relatively low, except for when SLB instances are used because SLB instances communicate with ECS instances on the intranet. Therefore, unexpected spikes in intranet traffic are usually caused by ECS instances copying data on the intranet. However, another common cause of intranet traffic spikes are virus attacks, which result in a spike of packet forwarding on the intranet. If a spike is caused by this particular issue, we recommend that you further monitor the specific processes occupying intranet traffic to revolve this problem.

If you are running Linux on your instance, you can install NetHogs on the system to view the specific processes occupying traffic.

```
#yum install nethogs Install NetHogs.
```

```
#nethogs eth0 View the specific traffic usage of the intranet NIC.
```

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6264/15532456344957_en-US.jpg) 

By using NetHogs, you can view intranet bandwidth usage by program and pinpoint which process or processes are occupying the intranet bandwidth.

If you are running Windows Server 2008 or later on your instance, you can go to the Resource Monitor to see the process or processes that occupy the bandwidth. Right-click on the instance's taskbar and select Start Task Manager \> Resource Monitor \> Network. Then, you can see the specific processes that are occupying network traffic.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6264/15532456344959_en-US.jpg)

