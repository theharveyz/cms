# 云监控Go语言版本插件安装 {#concept_hzh_l5w_wfb .concept}

## **Linux插件安装说明** {#section_pf5_z5w_wfb .section}

**说明：** 

1.  Go语言版本插件二进制文件命名

    ```
    `CmsGoAgent.linux-${ARCH}`
    ```

    其中ARCH根据Linux架构的不同，分为：amd64和386。

2.  版本号

    本文使用的插件版本为：2.1.47，建议您使用最新版本。


## 常用命令 {#section_u5x_qhx_wfb .section}

```
# 注册为系统服务
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH}install# 从系统服务中移除
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} uninstall
# 启动
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} start
# 停止
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} stop
# 重启
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} restart
# 卸载
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} stop && \
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH} uninstall && \
rm -rf /usr/local/cloudmonitor

```

## 安装命令 {#section_jpz_whx_wfb .section}

直接复制以下命令后在服务器上使用Root权限运行即可。

**说明：** 以下安装命令已在监控安装指引页面自动生成，您也可以去该页面直接复制使用。

**华北1 青岛 cn-qingdao**

```
REGION_ID=cn-qingdao VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-qingdao.oss-cn-qingdao-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华北2 北京 cn-beijing**

```
REGION_ID=cn-beijing VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-beijing.oss-cn-beijing-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华北3 张家口 cn-zhangjiakou**

```
REGION_ID=cn-zhangjiakou VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-zhangjiakou.oss-cn-zhangjiakou-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华北5 呼和浩特 cn-huhehaote**

```
REGION_ID=cn-huhehaote VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华东1 杭州 cn-hangzhou**

```
REGION_ID=cn-hangzhou VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华东2 上海 cn-shanghai**

```
REGION_ID=cn-shanghai VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-shanghai.oss-cn-shanghai-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华南1 深圳 cn-shenzhen**

```
REGION_ID=cn-shenzhen VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-shenzhen.oss-cn-shenzhen-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**香港 香港 cn-hongkong**

```
REGION_ID=cn-hongkong VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-hongkong.oss-cn-hongkong-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**美国西部1 硅谷 us-west-1**

```
REGION_ID=us-west-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-us-west-1.oss-us-west-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**美国东部1 弗吉尼亚 us-east-1**

```
REGION_ID=us-east-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-us-east-1.oss-us-east-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**亚太东南1 新加坡 ap-southeast-1**

```
REGION_ID=ap-southeast-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-ap-southeast-1.oss-ap-southeast-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**亚太东南2 悉尼 ap-southeast-2**

```
REGION_ID=ap-southeast-2 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**亚太东南3 吉隆坡 ap-southeast-3**

```
REGION_ID=ap-southeast-3 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**亚太东南5 雅加达 ap-southeast-5**

```
REGION_ID=ap-southeast-5 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-ap-southeast-5.oss-ap-southeast-5-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**亚太东北1 东京 ap-northeast-1**

```
REGION_ID=ap-northeast-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**亚太南部1 孟买 ap-south-1**

```
REGION_ID=ap-south-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-ap-south-1.oss-ap-south-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**欧洲中部1 法兰克福 eu-central-1**

```
REGION_ID=eu-central-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**欧洲西部 英国伦敦 eu-west-1**

```
REGION_ID=eu-west-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-eu-west-1.oss-eu-west-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**中东东部 迪拜 me-east-1**

```
REGION_ID=me-east-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-me-east-1.oss-me-east-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华东1金融云 杭州 cn-hangzhou**

```
REGION_ID=cn-hangzhou VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华东2金融云 上海 cn-shanghai-finance-1**

```
REGION_ID=cn-shanghai-finance-1 VERSION=2.1.47 \
bash -c "$(curl https://cms-agent-cn-shanghai-finance-1.oss-cn-shanghai-finance-1-pub-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

**华南1金融云 深圳 cn-shenzen-finance-1**

```
REGION_ID=cn-shenzhen-finance-1 VERSION=2.1.47 \
bash -c "$(curl http://cms-agent-cn-shenzhen-finance-1.oss-cn-shenzhen-finance-1-internal.aliyuncs.com/cms-go-agent/cms_go_agent_install.sh)"
```

## Windows插件安装说明 {#section_klb_xhx_wfb .section}

**安装步骤**

1.  根据系统情况（所在Region，主机类型），下载云监控插件[64位版本插件](http://cms-download.aliyun.com/cms-go-agent/2.1.47/CmsGoAgent.windows-amd64.exe)或[32位版本插件](http://cms-download.aliyun.com/cms-go-agent/2.1.47/CmsGoAgent.windows-386.exe) 到C:\\Program Files\\Alibaba\\cloudmonitor目录下。
2.  使用管理员权限启动命令提示符。
3.  输入并执行以下命令：

    ```
    cd"C:\Program Files\Alibaba\cloudmonitor"
    CmsGoAgent.windows-amd64.exe install
    CmsGoAgent.windows-amd64.exe start
    
    ```

4.  安装完成后，可以通过Windows系统的服务来查看、启动、停止云监控服务。

**卸载步骤**

1.  使用管理员权限启动命令提示符。
2.  输入并执行以下命令：

    ```
    cd"C:\Program Files\Alibaba\cloudmonitor"
    CmsGoAgent.windows-amd64.exe stop
    CmsGoAgent.windows-amd64.exe uninstall
    
    ```

3.  关闭命令提示符，将`C:\Program Files\Alibaba\cloudmonitor`整个目录删除。

**无公网下载**

如果没有公网可以通过内网地址下载，例如青岛64位安装包下载地址为：[http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/cms-go-agent/2.1.47/CmsGoAgent.windows-amd64.exe](http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.7/windows64/agent-windows64-1.3.7-package.zip)

-   可以通过修改两处cn-qingdao切换到其他region下载地址
-   可以通过将amd64修改为386来切换到32位版本
-   可以通过修改2.1.47切换到其他版本

**Region列表**

|Region中文名称|Region英文表示|城市|
|----------|----------|--|
|华北 1|cn-qingdao|青岛|
|华北 2|cn-beijing|北京|
|华北 3|cn-zhangjiakou|张家口|
|华北 5|cn-huhehaote|呼和浩特|
|华东 1|cn-hangzhou|杭州|
|华东 2|cn-shanghai|上海|
|华南 1|cn-shenzhen|深圳|
|香港|cn-hongkong|香港|
|美国西部 1|us-west-1|硅谷|
|美国东部 1|us-east-1|弗吉尼亚|
|亚太东南 1|ap-southeast-1|新加坡|
|亚太东南 2|ap-southeast-2|悉尼|
|亚太东南 3|ap-southeast-3|吉隆坡|
|亚太东南 5|ap-southeast-5|雅加达|
|亚太东北 1|ap-northeast-1|日本|
|亚太南部 1|ap-south-1|孟买|
|欧洲中部 1|eu-central-1|法兰克福|
|中东东部 1|me-east-1|迪拜|
|华东1金融云|cn-hangzhou|杭州|
|华东2金融云|cn-shanghai-finance-1|上海|
|华南1金融云|cn-shenzhen-finance-1|深圳|
|英国 伦敦|eu-west-1|伦敦|

## 安全配置说明 {#section_ev5_r4x_wfb .section}

以下是云监控插件与服务端交互用到的端口，这些端口被安全软件禁用后，会导致监控数据采集异常，如果您的ECS服务器对安全要求较高，需要针对具体IP地址放行，可以将下列IP加入白名单。

**说明：** 未来随着云监控版本的更新维护，可能会加入更多的IP地址或变更IP地址，为简化防火墙规则的配置，可以直接配置允许100.100网段的出方向，这个网段是阿里云内网保留网段，用于提供阿里云官方服务。

|端口|IP|方向|描述|
|--|--|--|--|
|31288080|100.100.19.43 cn-hangzhou 100.100.18.22 cn-beijing 100.100.36.102 cn-qingdao 100.100.0.13 cn-shenzhen 100.100.35.4 cn-hongkong 100.100.38.1 us-west-1 100.100.38.1 us-east-1 100.100.30.20 ap-southeast-1 100.100.36.11 cn-shanghai 100.100.80.184 ap-northeast1 100.100.80.241 eu-central-1 100.100.80.142 me-east-1 100.100.80.92 ap-southeast-2 100.100.80.92 cn-zhangjiakou 100.100.80.153 ap-southeast-3 100.100.80.135 cn-huhehaote 100.100.80.152 ap-south-1 100.100.80.160 ap-southeast-5 100.100.80.229 cn-chengdu 100.100.0.3 eu-west-1|出方向|用于插件升级，监控配置管理等管控类操作|
|80|100.100.0.19 cn-zhangjiakou 100.100.36.6 cn-shanghai 100.100.38.3 us-east-1 100.100.29.7 us-west-1 100.100.35.11 cn-hongkong 100.100.80.137 ap-northeast-1 100.100.80.72 eu-central-1 100.100.0.31 cn-shenzhen 100.100.18.50 cn-beijing 100.100.45.73 cn-hangzhou 100.100.15.23 cn-qingdao 100.100.80.151 me-east-1 100.100.80.13 ap-southeast-2 100.100.103.7 ap-southeast-1 100.100.80.140 ap-southeast-3 100.100.80.12 cn-huhehaote 100.100.80.66 ap-south-1 100.100.80.180 ap-southeast-5 100.100.80.14 cn-chengdu 100.100.0.2 eu-west-1|出方向|用于收集监控数据到云监控服务端|

**资源消耗**

-   插件安装包大小： 10~15MB。
-   内存：10~15MB，加上共享空间约为20MB（视您的系统内存的大小而有所不同）。
-   CPU：1~2%。
-   网络： 使用内网网络，不消耗公网流量。

**系统要求**

|操作系统|硬件架构|备注|
|----|----|--|
|Windows 7, Server 2008R2 or later|amd64, 386| |
|Linux 2.6.23 or later with glibc|amd64, 386|CentOS/RHEL 5.x not supported.|

**常见问题**

-   云监控日志位置：
    -   Linux：/usr/local/cloudmonitor/logs
    -   Windows：C:\\Program Files\\Alibaba\\cloudmonitor\\logs

