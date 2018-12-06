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
/usr/local/cloudmonitor/CmsGoAgent.linux-${ARCH}install
# 从系统服务中移除
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

如果没有公网可以通过内网地址下载，例如青岛64位安装包下载地址为：[http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/cms-go-agent/2.1.47/CmsGoAgent.windows-amd64.exe](http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/cms-go-agent/2.1.47/CmsGoAgent.windows-amd64.exe)

-   可以通过修改两处cn-qingdao切换到其他region下载地址
-   可以通过将amd64修改为386来切换到32位版本
-   可以通过修改2.1.47切换到其他版本

## 安全配置说明 {#section_ev5_r4x_wfb .section}

以下是云监控插件与服务端交互用到的端口，这些端口被安全软件禁用后，会导致监控数据采集异常，如果您的ECS服务器对安全要求较高，需要针对具体IP地址放行，可以将下列IP加入白名单。

**说明：** 

1.  未来随着云监控版本的更新维护，可能会加入更多的IP或变更IP地址，为简化防火墙规则的配置，可以直接配置允许100.0.0.0/8网段的出方向，这个网段是阿里云内网保留网段，用于提供阿里云官方服务。
2.  下表中被中括号括起来的IP地址，属可选部分，主要是作为网络不好情况下的备用地址。

|序号|Region|IP|方向|描述|
|--|------|--|--|--|
|1|cn-hangzhou华东 1杭州|100.100.19.43:3128|出方向|监控配置管理等管控类操作|
|100.100.45.73:80|出方向|收集监控数据到云监控服务端|
|2|cn-beijing华北 2北京|100.100.18.22:3128|出方向|监控配置管理等管控类操作|
|100.100.18.50:80|出方向|收集监控数据到云监控服务端|
|3|cn-qingdao华北 1青岛|100.100.36.102:3128|出方向|监控配置管理等管控类操作|
|100.100.15.23:80|出方向|收集监控数据到云监控服务端|
|4|cn-shenzhen华南 1深圳|100.100.0.13:3128|出方向|监控配置管理等管控类操作|
|100.100.0.31:80|出方向|收集监控数据到云监控服务端|
|5|cn-hongkong香港|100.103.0.47:3128|出方向|监控配置管理等管控类操作|
|100.103.0.45:80|出方向|收集监控数据到云监控服务端|
|6|cn-huhehaote华北 5呼和浩特|100.100.80.135:8080|出方向|监控配置管理等管控类操作|
|100.100.80.12:80|出方向|收集监控数据到云监控服务端|
|7|cn-zhangjiakou华北 3张家口|100.100.80.92:8080|出方向|监控配置管理等管控类操作|
|100.100.0.19:80|出方向|收集监控数据到云监控服务端|
|8|cn-shanghai华东 2上海|100.100.36.11:3128|出方向|监控配置管理等管控类操作|
|100.100.36.6:80|出方向|收集监控数据到云监控服务端|
|9|cn-chengdu西南 1成都|100.100.80.229:8080|出方向|监控配置管理等管控类操作|
|100.100.80.14:80|出方向|收集监控数据到云监控服务端|
|10|us-east-1美国东部 1弗吉尼亚|100.103.0.95:3128|出方向|监控配置管理等管控类操作|
|100.103.0.94:80|出方向|收集监控数据到云监控服务端|
|11|us-west-1美国西部 1硅谷|100.103.0.95:3128|出方向|监控配置管理等管控类操作|
|100.100.29.7:80|出方向|收集监控数据到云监控服务端|
|12|eu-central-1欧洲中部 1德国 法兰克福|100.100.80.241:8080|出方向|监控配置管理等管控类操作|
|100.100.80.72:80|出方向|收集监控数据到云监控服务端|
|13|eu-west-1英国 伦郭|100.100.0.3:8080|出方向|监控配置管理等管控类操作|
|100.100.0.2:80|出方向|收集监控数据到云监控服务端|
|14|ap-southeast-1亚太东南 1新加坡|100.100.30.20:3128|出方向|监控配置管理等管控类操作|
|100.100.103.7:80|出方向|收集监控数据到云监控服务端|
|15|ap-southeast-2亚太东南 2澳大利亚 悉尼|100.100.80.92:8080|出方向|监控配置管理等管控类操作|
| 100.100.80.13:80

 \[47.91.39.6:443\]

 |出方向|收集监控数据到云监控服务端|
|16|ap-southeast-3亚太东南 3吉隆坡|100.100.80.153:8080|出方向|监控配置管理等管控类操作|
|100.100.80.140:80|出方向|收集监控数据到云监控服务端|
|17|ap-southeast-5亚太东南 5雅加达|100.100.80.160:8080|出方向|监控配置管理等管控类操作|
|100.100.80.180:80|出方向|收集监控数据到云监控服务端|
|18|me-east-1中东东部 1迪拜|100.100.80.142:8080|出方向|监控配置管理等管控类操作|
| 100.100.80.151:80

 \[47.91.99.5:443\]

 |出方向|收集监控数据到云监控服务端|
|19|ap-northeast-1亚太东北 1日本 东京|100.100.80.184:8080|出方向|监控配置管理等管控类操作|
| 100.100.80.137:80

 \[47.91.8.7:443\]

 |出方向|收集监控数据到云监控服务端|
|20|ap-south-1亚太南部 1孟买|100.100.80.152:8080|出方向|监控配置管理等管控类操作|
|100.100.80.66:80|出方向|收集监控数据到云监控服务端|

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

