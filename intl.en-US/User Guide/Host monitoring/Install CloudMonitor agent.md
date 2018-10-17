# Install CloudMonitor agent {#concept_d5f_vhv_vdb .concept}

The agent of the Go programming language version is now available. If you do not want the server to introduce Java processes or if you want the agent to consume less resources, you can install this agent manually. For details, see [CloudMonitor agent of the Go programming language version](https://yq.aliyun.com/articles/628229).

## Install CloudMonitor agent on Linux {#section_vhm_3cf_xdb .section}

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

**Installation command **

Copy the following command and then run it on the server as the root user:

**North China 1 Qingdao cn-qingdao**

```

REGION_ID=cn-qingdao VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-qingdao.oss-cn-qingdao-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**North China 2 Beijing cn-beijing**

```

REGION_ID=cn-beijing VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-beijing.oss-cn-beijing-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**North China 3 Zhangjiakou cn-zhangjiakou**

```

REGION_ID=cn-zhangjiakou VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-zhangjiakou.oss-cn-zhangjiakou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**North China 5 Hohhot cn-huhehaote**

```

REGION_ID=cn-huhehaote VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East China 1 Hangzhou cn-hangzhou**

```

REGION_ID=cn-hangzhou VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East China 2 Shanghai cn-shanghai**

```

REGION_ID=cn-shanghai VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-shanghai.oss-cn-shanghai-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**South China 1 Shenzhen cn-shenzhen**

```

REGION_ID=cn-shenzhen VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-shenzhen.oss-cn-shenzhen-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Hong Kong Hong Kong cn-hongkong**

```

REGION_ID=cn-hongkong VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-hongkong.oss-cn-hongkong-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**West US 1 Silicon Valley us-west-1**

```

REGION_ID=us-west-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-us-west-1.oss-us-west-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East US 1 Virginia us-east-1**

```

REGION_ID=us-east-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-us-east-1.oss-us-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 1 Singapore ap-southeast-1**

```

REGION_ID=ap-southeast-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-1.oss-ap-southeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 2 Sydney ap-southeast-2**

```

REGION_ID=ap-southeast-2 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 3 Kuala Lumpur ap-southeast-3**

```

REGION_ID=ap-southeast-3 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 5 Jakarta ap-southeast-5**

```

REGION_ID=ap-southeast-5 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-southeast-5.oss-ap-southeast-5-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Northeast 1 Tokyo ap-northeast-1**

```

REGION_ID=ap-northeast-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific South 1 Mumbai ap-south-1**

```

REGION_ID=ap-south-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-ap-south-1.oss-ap-south-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Central Europe 1 Frankfurt eu-central-1**

```

REGION_ID=eu-central-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Western Europe, London, England eu-west-1**

```

REGION_ID=eu-west-1 VERSION=1.3.7 \ bash -c "$(curl https://cms-agent-eu-west-1.oss-eu-west-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Eastern Middle East Dubai me-east-1**

```

REGION_ID=me-east-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-me-east-1.oss-me-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East China 1 Finance Cloud Hangzhou cn-hangzhou**

```

REGION_ID=cn-hangzhou VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East China 2 Finance Cloud Shanghai cn-shanghai-finance-1**

```

REGION_ID=cn-shanghai-finance-1 VERSION=1.3.7 \
bash -c "$(curl https://cms-agent-cn-shanghai-finance-1.oss-cn-shanghai-finance-1-pub-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**South China 1 Finance Cloud Shenzhen cn-shenzen-finance-1**

```

REGION_ID=cn-shenzhen-finance-1 VERSION=1.3.7 \
bash -c "$(curl http://cms-agent-cn-shenzhen-finance-1.oss-cn-shenzhen-finance-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

## Install CloudMonitor agent on Windows {#section_fxr_wdf_xdb .section}

**Installation procedure**

1.  Download [64-bit version agent](http://cms-download.aliyun.com/release/1.3.7/windows64/agent-windows64-1.3.7-package.zip) or [32-bit version agent](http://cms-download.aliyun.com/release/1.3.7/windows32/agent-windows32-1.3.7-package.zip).
2.  Create a folder and name it cloudmonitor in the path C:/Program Files/Alibaba.
3.  Decompress the package to C:/Program Files/Alibaba/cloudmonitor.
4.  Double-click C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/InstallApp-NT.bat to install CloudMonitor as the administrator.
5.  Double-click C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/StartApp-NT.bat to start CloudMonitor as the administrator.
6.  After the installation is complete, you can view, start, and stop the CloudMonitor application from the service panel of Windows.

**Uninstall procedure**

1.  Stop the CloudMonitor application from the service panel of Windows.
2.  Run C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/UninstallApp-NT.bat to delete the CloudMonitor application as the administrator.
3.  In the installation directory, delete the entire directory C:/Program Files/Alibaba/cloudmonitor.

**Download with no public network**

If there is no public network, you can download the package from the Intranet. For example, the download address of Qingdao 64-bit installation package is: [http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.7/windows64/agent-windows64-1.3.7-package.zip](http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.7/windows64/agent-windows64-1.3.7-package.zip)

-   For the download address of another region, change "cn-qingdao" both in the preceding example.
-   For the download address of Windows 32-bit version, change "windows64" both to "windows32" in the preceding example.
-   For the download address of another version, change "1.3.7" both in the preceding example.

**Region list**

|**Region**|**Region description**|**City**|
|:---------|:---------------------|:-------|
|North China 1|cn-qingdao|Qingdao|
|North China 2|cn-beijing|Beijing|
|North China 3|cn-zhangjiakou |Zhangjiakou|
|North China 5|cn-huhehaote|Hohhot|
|East China 1|cn-hangzhou|Hangzhou|
|East China 2|cn-shanghai|Shanghai|
|South China 1|cn-shenzhen|Shenzhen|
|Hong Kong|cn-hongkong|Hong Kong|
|West US 1|us-west-1|Silicon Valley|
|East US 1|us-east-1|Virginia|
|Asia Pacific Southeast 1|Ap-southeast-1 |Singapore|
|Asia Pacific Southeast 2|ap-southeast-2 |Sydney|
|Asia Pacific Southeast 3|ap-southeast-3|Kuala Lumpur|
|Asia Pacific Southeast 5|ap-southeast-5|Jakarta|
|Asia Pacific Northeast 1|ap-northeast-1|Japan|
|Asia Pacific South 1 |ap-south-1|Mumbai |
|Central Europe 1|eu-central-1|Frankfurt|
|Eastern Middle East 1|me-east-1 |Dubai|
|East China 1 Finance Cloud|cn-hangzhou|Hangzhou|
|East China 2 Finance Cloud|cn-shanghai-finance-1|Shanghai|
|South China 1 Finance Cloud|cn-shenzhen-finance-1|Shenzhen|
|London, England|eu-west-1|London|

## **Security configuration instructions** {#section_s5t_313_p2b .section}

The following table lists the ports that the CloudMonitor agent uses to interact with the server. If these ports are disabled by the security software, monitoring data may fail to be collected. If your ECS server requires a higher level of security, you can add the following IP addresses to the white list.

**Note:** Future updates and maintenance of the CloudMonitor version may add more IP addresses or change the IP addresses. To simplify the configuration of the firewall rules, you can directly allow the outbound direction of the 100.100 network segment, which is reserved for the intranet of Alibaba Cloud and used to provide official Alibaba Cloud services, with no security issues in general.

|Port|IP address|Direction|Description|
|32000|127.0.0.1|Inbound, outbound|Bound to 127.0.0.1, used for CloudMonitor agent process Daemon|
|3128, 8080| 100.100.19.43 cn-hangzhou

 100.100.18.22 cn-beijing

 100.100.36.102 cn-qingdao

 100.100.0.13 cn-shenzhen

 100.100.35.4 cn-hongkong

 100.100.38.1 us-west-1

 100.100.38.1 us-east-1

 100.100.30.20 ap-southeast-1

 100.100.36.11 cn-shanghai

 100.100.80.184 ap-northeast-1

 100.100.80.241 eu-central-1

 100.100.80.142 me-east-1

 100.100.80.92 ap-southeast-2

 100.100.80.92 cn-zhangjiakou

 100.100.80.153 ap-southeast-3

 100.100.80.135 cn-huhehaote

 100.100.80.152 ap-south-1

 100.100.80.160 ap-southeast-5

 100.100.80.229 cn-chengdu

 100.100.0.3 eu-west-1

 |Outbound|Used for agent upgrade, monitoring configuration management, and other management and control operations|
|80| 100.100.0.19 cn-zhangjiakou

 100.100.36.6 cn-shanghai

 100.100.38.3 us-east-1

 100.100.29.7 us-west-1

 100.100.35.11 cn-hongkong

 100.100.80.137 ap-northeast-1

 100.100.80.72 eu-central-1

 100.100.0.31 cn-shenzhen

 100.100.18.50 cn-beijing

 100.100.45.73 cn-hangzhou

 100.100.15.23 cn-qingdao

 100.100.80.151 me-east-1

 100.100.80.13 ap-southeast-2

 100.100.103.7 ap-southeast-1

 100.100.80.140 ap-southeast-3

 100.100.80.12 cn-huhehaote

 100.100.80.66 ap-south-1

 100.100.80.180 ap-southeast-5

 100.100.80.14 cn-chengdu

 100.100.0.2 eu-west-1

 |Outbound|Used to collect monitoring data to the CloudMonitor server|

## Resource consumption {#section_oh3_r3f_xdb .section}

-   Installation package size: 75 M
-   Space occupied after installation: 200 M
-   Memory: 64 M
-   CPU: less than 1%
-   Network: Intranet, with no public network bandwidth consumption

## FAQs {#section_vv2_nff_xdb .section}

-   Where are CloudMonitor logs saved?
    -   Linux: /usr/local/cloudmonitor/logs
    -   Windows: C:/Program Files/Alibaba/cloudmonitor/logs

-   What should I do if there is a conflict between the port occupied by the agent and the port used by my service?

    1.  Change the port range by modifying the CloudMonitor configuration, with the file location: /usr/local/cloudmonitor/wrapper/conf/wrapper.conf
    2.  Restart CloudMonitor
    ```
    
    wrapper.port.min=40000
    wrapper.port.max=41000
    wrapper.jvm.port.min=41001
    wrapper.jvm.port.max=42000
    ```


