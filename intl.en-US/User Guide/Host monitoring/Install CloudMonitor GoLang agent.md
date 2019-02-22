# Install CloudMonitor GoLang agent {#concept_hzh_l5w_wfb .concept}

## Requirements on systems {#section_plr_5l3_wgb .section}

|Operating system|Hardware architecture|Note|
|----------------|---------------------|----|
|Windows 7, Windows Server 2008 R2, or later versions|amd64, 386|None|
|Linux 2.6.23 or later with glibc|amd64, 386|CentOS/RHEL 5.x are not supported.|

**Resource usage**

-   Installation package size: 10–15 MB
-   Memory: 10–15 MB, or 20 MB if you include shared space. Actual numbers vary depending on the size of your system memory.
-   CPU: 1–2%
-   Network: intranet. No Internet bandwidth is used.

## Install a CloudMonitor GoLang agent on Linux {#section_pf5_z5w_wfb .section}

**Note:** 

1.  The binary file name of the agent

    ```
    `CmsGoAgent.linux-${ARCH}`
    ```

    The value of "ARCH" can be "amd64" or "386" depending on the architecture of your Linux system.

2.  Version

    In this topic, the version 2.1.55 is used. We recommend that you use the latest version. You can find the number of the latest version on the host monitoring page in the CloudMonitor console.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64886/155081609834123_en-US.png)


**Frequently used commands**

```
# Register the agent as a system service.
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH}install
# Remove the agent from system services.
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} uninstall
# Start the agent.
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} start
# Stop the agent.
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} stop
# Restart the agent.
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} restart
# Uninstall the agent.
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} stop && \
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} uninstall && \
rm -rf /usr/local/cloudmonitor

```

**Installation command**

Copy the installation command of the region you require and then run the command on your server with root permissions.

**Note:** You can also find the command on the Monitor Install Guide page in the CloudMonitor console.

**China North 1 \(Qingdao\) cn-qingdao**

```
REGION_ID=cn-qingdao VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-qingdao.oss-cn-qingdao-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China North 2 \(Beijing\) cn-beijing**

```
REGION_ID=cn-beijing VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-beijing.oss-cn-beijing-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China North 3 \(Zhangjiakou\) cn-zhangjiakou**

```
REGION_ID=cn-zhangjiakou VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-zhangjiakou.oss-cn-zhangjiakou-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China North 5 \(Hohhot\) cn-huhehaote**

```
REGION_ID=cn-huhehaote VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China East 1 \(Hangzhou\) cn-hangzhou**

```
REGION_ID=cn-hangzhou VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China East 2 \(Shanghai\) cn-shanghai**

```
REGION_ID=cn-shanghai VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-shanghai.oss-cn-shanghai-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China South 1 \(Shenzhen\) cn-shenzhen**

```
REGION_ID=cn-shenzhen VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-shenzhen.oss-cn-shenzhen-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Hong Kong \(China\) cn-hongkong**

```
REGION_ID=cn-hongkong VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-hongkong.oss-cn-hongkong-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**US West 1 \(Silicon Valley\) us-west-1**

```
REGION_ID=us-west-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-us-west-1.oss-us-west-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**US East 1 \(Virginia\) us-east-1**

```
REGION_ID=us-east-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-us-east-1.oss-us-east-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Asia Pacific SE 1 \(Singapore\) ap-southeast-1**

```
REGION_ID=ap-southeast-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-ap-southeast-1.oss-ap-southeast-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Asia Pacific SE 2 \(Sydney\) ap-southeast-2**

```
REGION_ID=ap-southeast-2 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Asia Pacific SE 3 \(Kuala Lumpur\) ap-southeast-3**

```
REGION_ID=ap-southeast-3 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Asia Pacific SE 5 \(Jakarta\) ap-southeast-5**

```
REGION_ID=ap-southeast-5 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-ap-southeast-5.oss-ap-southeast-5-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Asia Pacific NE 1 \(Tokyo\) ap-northeast-1**

```
REGION_ID=ap-northeast-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Asia Pacific SOU 1 \(Mumbai\) ap-south-1**

```
REGION_ID=ap-south-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-ap-south-1.oss-ap-south-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**EU Central 1 \(Frankfurt\) eu-central-1**

```
REGION_ID=eu-central-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**UK \(London\) eu-west-1**

```
REGION_ID=eu-west-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-eu-west-1.oss-eu-west-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**Middle East 1 \(Dubai\) me-east-1**

```
REGION_ID=me-east-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-me-east-1.oss-me-east-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China East 1 Finance Cloud \(Hangzhou\) cn-hangzhou**

```
REGION_ID=cn-hangzhou VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China East 2 Finance Cloud \(Shanghai\) cn-shanghai-finance-1**

```
REGION_ID=cn-shanghai-finance-1 VERSION=2.1.55 \
bash -c "$(curl https://cms-agent-cn-shanghai-finance-1.oss-cn-shanghai-finance-1-pub-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**China South 1 Finance Cloud \(Shenzhen\) cn-shenzen-finance-1**

```
REGION_ID=cn-shenzhen-finance-1 VERSION=2.1.55 \
bash -c "$(curl http://cms-agent-cn-shenzhen-finance-1.oss-cn-shenzhen-finance-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

## Install a CloudMonitor GoLang agent on Windows {#section_klb_xhx_wfb .section}

**Installation procedure**

1.  Select your region and host type. Then, depending on your operating system version, download a [64-bit agent version](http://cms-download.aliyun.com/cms-go-agent/2.1.47/CmsGoAgent.windows-amd64.exe) or [32-bit agent version](http://cms-download.aliyun.com/cms-go-agent/2.1.47/CmsGoAgent.windows-386.exe) and save it in C:\\Program Files\\Alibaba\\cloudmonitor.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64886/155081609838125_en-US.png)

2.  Open the **Command Prompt** as an administrator.
3.  Run the following command:

    ```
    cd"C:\Program Files\Alibaba\cloudmonitor"
    CmsGoAgent.windows-amd64.exe install
    CmsGoAgent.windows-amd64.exe start
    
    ```

4.  After the installation is complete, you can use **Windows Services** to view, start, and stop the agent.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64886/155081609834124_en-US.png)


**Uninstall procedure**

1.  Open the **Command Prompt** as an administrator.
2.  Run the following command:

    ```
    cd"C:\Program Files\Alibaba\cloudmonitor"
    CmsGoAgent.windows-amd64.exe stop
    CmsGoAgent.windows-amd64.exe uninstall
    
    ```

3.  Close the **Command Prompt**, and delete the directory `C:\Program Files\Alibaba\cloudmonitor`.

**Download the agent with no Internet connection**

If you do not have an Internet connection, you can download the installation package from the intranet. For example, if the region of your host is Qingdao and the host uses a 64-bit system, then the intranet download address is as follows: [http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/cms-go-agent/2.1.55/CmsGoAgent.windows-amd64.exe](http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/cms-go-agent/2.1.47/CmsGoAgent.windows-amd64.exe).

-   For a host in another region, change "cn-qingdao" to the corresponding region ID.
-   For a host that uses a 32-bit system, change "amd64" to "386".
-   For another version, change "2.1.55" to the corresponding version number.

## Security configuration instructions {#section_ev5_r4x_wfb .section}

The following table lists the ports that the CloudMonitor agent uses to interact with your server. Note that monitoring data may not be collected if these ports are disabled by security software. Therefore, in the case that your ECS server requires a higher level of security, we recommend that you add one of the following IP addresses to your whitelist.

**Note:** 

1.  Future maintenance and version updates of CloudMonitor may cause changes to the following IP addresses. Therefore, to simplify the configuration of your firewall rules, we recommend that you directly allow the 100.0.0.0/8 CIDR block in the egress direction. This CIDR block is reserved for the intranet of Alibaba Cloud and is free of security issues.
2.  The IP addresses in square brackets \(\[ \]\) are optional. They can be used as backup addresses in the situation that your network connection is poor.

|Region|IP|Direction|Description|
|------|--|---------|-----------|
|China East 1 \(Hangzhou\) cn-hangzhou|100.100.19.43:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.45.73:80|Egress|Used to collect monitoring data to CloudMonitor|
|China North 2 \(Beijing\) cn-beijing|100.100.18.22:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.18.50:80|Egress|Used to collect monitoring data to CloudMonitor|
|China North 1 \(Qingdao\) cn-qingdao|100.100.36.102:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.15.23:80|Egress|Used to collect monitoring data to CloudMonitor|
|China South 1 \(Shenzhen\) cn-shenzhen|100.100.0.13:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.0.31:80|Egress|Used to collect monitoring data to CloudMonitor|
|Hong Kong \(China\) cn-hongkong|100.103.0.47:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.103.0.45:80|Egress|Used to collect monitoring data to CloudMonitor|
|China North 5 \(Hohhot\) cn-huhehaote|100.100.80.135:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.80.12:80|Egress|Used to collect monitoring data to CloudMonitor|
|China North 3 \(Zhangjiakou\) cn-zhangjiakou|100.100.80.92:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.0.19:80|Egress|Used to collect monitoring data to CloudMonitor|
|China East 2 \(Shanghai\) cn-shanghai|100.100.36.11:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.36.6:80|Egress|Used to collect monitoring data to CloudMonitor|
|China SW 1 \(Chengdu\) cn-chengdu|100.100.80.229:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.80.14:80|Egress|Used to collect monitoring data to CloudMonitor|
|US East 1 \(Virginia\) us-east-1|100.103.0.95:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.103.0.94:80|Egress|Used to collect monitoring data to CloudMonitor|
|US West 1 \(Silicon Valley\) us-west-1|100.103.0.95:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.29.7:80|Egress|Used to collect monitoring data to CloudMonitor|
|EU Central 1 \(Frankfurt\) eu-central-1|100.100.80.241:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.80.72:80|Egress|Used to collect monitoring data to CloudMonitor|
|UK \(London\) eu-west-1|100.100.0.3:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.0.2:80|Egress|Used to collect monitoring data to CloudMonitor|
|Asia Pacific SE 1 \(Singapore\) ap-southeast-1|100.100.30.20:3128|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.103.7:80|Egress|Used to collect monitoring data to CloudMonitor|
|Asia Pacific SE 2 \(Sydney\) ap-southeast-2|100.100.80.92:8080|Egress|Used for monitoring configuration management, and other management and control operations|
| 100.100.80.13:80

 \[47.91.39.6:443\]

 |Egress|Used to collect monitoring data to CloudMonitor|
|Asia Pacific SE 3 \(Kuala Lumpur\) ap-southeast-3|100.100.80.153:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.80.140:80|Egress|Used to collect monitoring data to CloudMonitor|
|Asia Pacific SE 5 \(Jakarta\) ap-southeast-5|100.100.80.160:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.80.180:80|Egress|Used to collect monitoring data to CloudMonitor|
|Middle East 1 \(Dubai\) me-east-1|100.100.80.142:8080|Egress|Used for monitoring configuration management, and other management and control operations|
| 100.100.80.151:80

 \[47.91.99.5:443\]

 |Egress|Used to collect monitoring data to CloudMonitor|
|Asia Pacific NE 1 \(Tokyo\) ap-northeast-1|100.100.80.184:8080|Egress|Used for monitoring configuration management, and other management and control operations|
| 100.100.80.137:80

 \[47.91.8.7:443\]

 |Egress|Used to collect monitoring data to CloudMonitor|
|Asia Pacific SOU 1 \(Mumbai\) ap-south-1|100.100.80.152:8080|Egress|Used for monitoring configuration management, and other management and control operations|
|100.100.80.66:80|Egress|Used to collect monitoring data to CloudMonitor|

**FAQ**

-   Where are CloudMonitor logs saved?
    -   Linux: /usr/local/cloudmonitor/logs
    -   Windows: C:\\Program Files\\Alibaba\\cloudmonitor\\logs

