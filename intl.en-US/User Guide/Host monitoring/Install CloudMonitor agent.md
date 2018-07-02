# Install CloudMonitor agent {#concept_d5f_vhv_vdb .concept}

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

REGION_ID=cn-qingdao VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-qingdao.oss-cn-qingdao-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**North China 2 Beijing cn-beijing**

```

REGION_ID=cn-beijing VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-beijing.oss-cn-beijing-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**North China 3 Zhangjiakou cn-zhangjiakou**

```

REGION_ID=cn-zhangjiakou VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-zhangjiakou.oss-cn-zhangjiakou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**North China 5 Hohhot cn-huhehaote**

```

REGION_ID=cn-huhehaote VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East China 1 Hangzhou cn-hangzhou**

```

REGION_ID=cn-hangzhou VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East China 2 Shanghai cn-shanghai**

```

REGION_ID=cn-shanghai VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-shanghai.oss-cn-shanghai-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**South China 1 Shenzhen cn-shenzhen**

```

REGION_ID=cn-shenzhen VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-shenzhen.oss-cn-shenzhen-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Hong Kong Hong Kong cn-hongkong**

```

REGION_ID=cn-hongkong VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-hongkong.oss-cn-hongkong-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**West US 1 Silicon Valley us-west-1**

```

REGION_ID=us-west-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-us-west-1.oss-us-west-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**East US 1 Virginia us-east-1**

```

REGION_ID=us-east-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-us-east-1.oss-us-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 1 Singapore ap-southeast-1**

```

REGION_ID=ap-southeast-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-1.oss-ap-southeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 2 Sydney ap-southeast-2**

```

REGION_ID=ap-southeast-2 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 3 Kuala Lumpur ap-southeast-3**

```

REGION_ID=ap-southeast-3 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Southeast 5 Jakarta ap-southeast-5**

```

REGION_ID=ap-southeast-5 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-5.oss-ap-southeast-5-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific Northeast 1 Tokyo ap-northeast-1**

```

REGION_ID=ap-northeast-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Asia Pacific South 1 Mumbai ap-south-1**

```

REGION_ID=ap-south-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-south-1.oss-ap-south-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**Central Europe 1 Frankfurt eu-central-1**

```

REGION_ID=eu-central-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)""
```

**Eastern Middle East Dubai me-east-1**

```

REGION_ID=me-east-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-me-east-1.oss-me-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

## Install CloudMonitor agent on Windows {#section_fxr_wdf_xdb .section}

**Installation procedure**

1.  Download [64-bit version Agent](http://cms-download.aliyun.com/release/1.3.2/windows64/agent-windows64-1.3.2-package.zip) or [32-bit version Agent](http://cms-download.aliyun.com/release/1.3.2/windows32/agent-windows32-1.3.2-package.zip).
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

If there is no public network, you can download the package from the Intranet. For example, the download address of Qingdao 64-bit installation package is: [http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.2/windows64/agent-windows64-1.3.2-package.zip](http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.2/windows64/agent-windows64-1.3.2-package.zip)

-   For the download address of another region, change "cn-qingdao" both in the preceding example.
-   For the download address of Windows 32-bit version, change "windows64" both to "windows32" in the preceding example.
-   For the download address of another version, change "1.3.2" both in the preceding example.

**Region list**

|**Region name**|**Region description**|**City**|
|:--------------|:---------------------|:-------|
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
|Asia Pacific Southeast 1|ap-southeast-1|Singapore|
|Asia Pacific Southeast 2|ap-southeast-2 |Sydney|
|Asia Pacific Southeast 3|ap-southeast-3|Kuala Lumpur|
|Asia Pacific Southeast 5|ap-southeast-5|Jakarta|
|Asia Pacific Northeast 1|ap-northeast-1 |Japan|
|Asia Pacific South 1 |ap-south-1|Mumbai|
|Central Europe 1|eu-central-1|Frankfurt|
|Eastern Middle East 1|me-east-1 |Dubai|

## Resource consumption {#section_oh3_r3f_xdb .section}

-   Installation package size: 75 M
-   Space occupied after installation: 200 M
-   Memory: 64 M
-   CPU: less than 1%
-   Network: Intranet, with no public network bandwidth consumption

## FAQs {#section_vv2_nff_xdb .section}

-   CloudMonitor log location
-   -   Linux: /usr/local/cloudmonitor/logs
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


