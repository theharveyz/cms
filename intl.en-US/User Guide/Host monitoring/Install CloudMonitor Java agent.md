# Install CloudMonitor Java agent {#concept_d5f_vhv_vdb .concept}

## Install a CloudMonitor Java agent on Linux {#section_vhm_3cf_xdb .section}

**Frequently used commands**

```
# Running status
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh status

# Start
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh start

# Stop
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh stop

# Restart
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh restart

# Uninstall
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh remove && \
rm -rf /usr/local/cloudmonitor
```

**Installation command**

This command varies by region. Copy the corresponding command and then run it on your server as a root user.

**China North 1 \(Qingdao\) cn-qingdao**

```

REGION_ID=cn-qingdao VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-qingdao.oss-cn-qingdao-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China North 2 \(Beijing\) cn-beijing**

```

REGION_ID=cn-beijing VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-beijing.oss-cn-beijing-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China North 3 \(Zhangjiakou\) cn-zhangjiakou**

```

REGION_ID=cn-zhangjiakou VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-zhangjiakou.oss-cn-zhangjiakou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China North 5 \(Hohhot\) cn-huhehaote**

```

REGION_ID=cn-huhehaote VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China East 1 \(Hangzhou\) cn-hangzhou**

```

REGION_ID=cn-hangzhou VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China East 2 \(Shanghai\) cn-shanghai**

```

REGION_ID=cn-shanghai VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-shanghai.oss-cn-shanghai-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China South 1 \(Shenzhen\) cn-shenzhen**

```

REGION_ID=cn-shenzhen VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-shenzhen.oss-cn-shenzhen-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Hong Kong \(China\) cn-hongkong**

```

REGION_ID=cn-hongkong VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-hongkong.oss-cn-hongkong-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**US West 1 \(Silicon Valley\) us-west-1**

```

REGION_ID=us-west-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-us-west-1.oss-us-west-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**US East 1 \(Virginia\) us-east-1**

```

REGION_ID=us-east-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-us-east-1.oss-us-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific SE 1 \(Singapore\) ap-southeast-1**

```

REGION_ID=ap-southeast-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-1.oss-ap-southeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific SE 2 \(Sydney\) ap-southeast-2**

```

REGION_ID=ap-southeast-2 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific SE 3 \(Kuala Lumpur\) ap-southeast-3**

```

REGION_ID=ap-southeast-3 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific SE 5 \(Jakarta\) ap-southeast-5**

```

REGION_ID=ap-southeast-5 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-5.oss-ap-southeast-5-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific NE 1 \(Tokyo\) ap-northeast-1**

```

REGION_ID=ap-northeast-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific SOU 1 \(Mumbai\) ap-south-1**

```

REGION_ID=ap-south-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-south-1.oss-ap-south-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**EU Central 1 \(Frankfurt\) eu-central-1**

```

REGION_ID=eu-central-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**UK \(London\) eu-west-1**

```

REGION_ID=eu-west-1 VERSION=1.3.7 \ bash -c "$(curl https://cms-agent-eu-west-1.oss-eu-west-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Middle East 1 \(Dubai\) me-east-1**

```

REGION_ID=me-east-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-me-east-1.oss-me-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China East 1 Finance Cloud \(Hangzhou\) cn-hangzhou**

```

REGION_ID=cn-hangzhou VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China East 2 Finance Cloud \(Shanghai\) cn-shanghai-finance-1**

```

REGION_ID=cn-shanghai-finance-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-shanghai-finance-1.oss-cn-shanghai-finance-1-pub-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**China South 1 Finance Cloud \(Shenzhen\) cn-shenzen-finance-1**

```

REGION_ID=cn-shenzhen-finance-1 VERSION=1.3.7 \
bash -c "$(curl http://cms-agent-cn-shenzhen-finance-1.oss-cn-shenzhen-finance-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

## Install a CloudMonitor Java agent on Windows {#section_fxr_wdf_xdb .section}

**Installation procedure**

1.  Download [64-bit agent version](http://cms-download.aliyun.com/release/1.3.7/windows64/agent-windows64-1.3.7-package.zip) or [32-bit agent version](http://cms-download.aliyun.com/release/1.3.7/windows32/agent-windows32-1.3.7-package.zip) based on your operating system version.
2.  Create a folder in the path C:/Program Files/Alibaba and name it cloudmonitor.
3.  Decompress the installation package to C:/Program Files/Alibaba/cloudmonitor.
4.  Double-click C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/InstallApp-NT.bat as an administrator to install CloudMonitor.
5.  Double-click C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/StartApp-NT.bat as an administrator to start CloudMonitor.
6.  After the installation is complete, you can view, start, and stop CloudMonitor through the service panel of Windows.

**Uninstall procedure**

1.  Stop CloudMonitor through the service panel of Windows.
2.  Run C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/UninstallApp-NT.bat as an administrator to delete CloudMonitor.
3.  In the installation directory, delete the entire directory C:/Program Files/Alibaba/cloudmonitor.

**Download the agent with no Internet connection**

If you do not have an Internet connection, you can download the installation package from the intranet. For example, if the region of your host is Qingdao and the host uses a 64-bit system, then the intranet download address is as follows: [http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.7/windows64/agent-windows64-1.3.7-package.zip](http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.7/windows64/agent-windows64-1.3.7-package.zip).

-   For a host in another region, change `cn-qingdao` to the corresponding region ID.
-   For a host that uses a 32-bit system, change `windows64` to `windows32`.
-   For another version, change `1.3.7` to the corresponding version number.

## **Security configuration instructions** {#section_s5t_313_p2b .section}

The following table lists the ports that the CloudMonitor agent uses to interact with your server. If the security software disables these ports, monitoring data may fail to be collected. If your ECS server requires a high level of security, you can add one of the following IP addresses to the whitelist.

**Note:** Future version updates and maintenance of CloudMonitor may cause changes to the following IP addresses. To simplify the configuration of your firewall rules, we recommend that you directly allow the 100.100 network segment in the egress direction. This network segment is reserved for the intranet of Alibaba Cloud with no security issues.

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

## Resource consumption {#section_oh3_r3f_xdb .section}

-   Installation package size: 75 MB
-   Space occupied after installation: 200 MB
-   Memory: 64 MB
-   CPU: less than 1%
-   Network: intranet, with no Internet bandwidth consumption

## FAQ {#section_vv2_nff_xdb .section}

-   Where are CloudMonitor logs saved?
    -   Linux: /usr/local/cloudmonitor/logs
    -   Windows: C:/Program Files/Alibaba/cloudmonitor/logs

-   What should I do if there is a conflict between the port occupied by the agent and the port used by my service?

    1.  Change the port range by modifying the CloudMonitor configuration, with the file location: /usr/local/cloudmonitor/wrapper/conf/wrapper.conf.
    2.  Restart CloudMonitor.
    ```
    
    wrapper.port.min=40000
    wrapper.port.max=41000
    wrapper.jvm.port.min=41001
    wrapper.jvm.port.max=42000
    ```


