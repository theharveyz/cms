# 云监控Agent安装 {#concept_d5f_vhv_vdb .concept}

## Linux Agent 安装说明 {#section_vhm_3cf_xdb .section}

**常用命令**

```
# 运行状态
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh status

# 启动
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh start

# 停止
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh stop

# 重启
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh restart

# 卸载
/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh remove && \
rm -rf /usr/local/cloudmonitor
```

**安装命令**

直接复制以下命令后在服务器上使用root权限运行即可。

**华北1 青岛 cn-qingdao**

```

REGION_ID=cn-qingdao VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-qingdao.oss-cn-qingdao-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华北2 北京 cn-beijing**

```

REGION_ID=cn-beijing VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-beijing.oss-cn-beijing-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华北3 张家口 cn-zhangjiakou**

```

REGION_ID=cn-zhangjiakou VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-zhangjiakou.oss-cn-zhangjiakou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华北5 呼和浩特 cn-huhehaote**

```

REGION_ID=cn-huhehaote VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华东1 杭州 cn-hangzhou**

```

REGION_ID=cn-hangzhou VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华东2 上海 cn-shanghai**

```

REGION_ID=cn-shanghai VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-shanghai.oss-cn-shanghai-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华南1 深圳 cn-shenzhen**

```

REGION_ID=cn-shenzhen VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-shenzhen.oss-cn-shenzhen-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**香港 香港 cn-hongkong**

```

REGION_ID=cn-hongkong VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-hongkong.oss-cn-hongkong-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**美国西部1 硅谷 us-west-1**

```

REGION_ID=us-west-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-us-west-1.oss-us-west-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**美国东部1 弗吉尼亚 us-east-1**

```

REGION_ID=us-east-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-us-east-1.oss-us-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**亚太东南1 新加坡 ap-southeast-1**

```

REGION_ID=ap-southeast-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-1.oss-ap-southeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**亚太东南2 悉尼 ap-southeast-2**

```

REGION_ID=ap-southeast-2 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**亚太东南3 吉隆坡 ap-southeast-3**

```

REGION_ID=ap-southeast-3 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**亚太东南5 雅加达 ap-southeast-5**

```

REGION_ID=ap-southeast-5 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-southeast-5.oss-ap-southeast-5-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**亚太东北1 东京 ap-northeast-1**

```

REGION_ID=ap-northeast-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**亚太南部1 孟买 ap-south-1**

```

REGION_ID=ap-south-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-ap-south-1.oss-ap-south-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**欧洲中部1 法兰克福 eu-central-1**

```

REGION_ID=eu-central-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)""
```

**中东东部 迪拜 me-east-1**

```

REGION_ID=me-east-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-me-east-1.oss-me-east-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华东1金融云 杭州 cn-hangzhou**

```

REGION_ID=cn-hangzhou VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-hangzhou.oss-cn-hangzhou-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华东2金融云 上海 cn-shanghai-finance-1**

```

REGION_ID=cn-shanghai-finance-1 VERSION=1.3.2 \
bash -c "$(curl https://cms-agent-cn-shanghai-finance-1.oss-cn-shanghai-finance-1-pub-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

**华南1金融云 深圳 cn-shenzen-finance-1**

```

REGION_ID=cn-shenzhen-finance-1 VERSION=1.3.2 \
bash -c "$(curl http://cms-agent-cn-shenzhen-finance-1.oss-cn-shenzhen-finance-1-internal.aliyuncs.com/release/cms_install_for_linux.sh)"
```

## Windows Agent 安装说明 {#section_fxr_wdf_xdb .section}

**安装步骤**

1.  根据系统情况，下载云监控Agent [64位版本Agent](http://cms-download.aliyun.com/release/1.3.2/windows64/agent-windows64-1.3.2-package.zip)或[32位版本Agent](http://cms-download.aliyun.com/release/1.3.2/windows32/agent-windows32-1.3.2-package.zip)。
2.  在C:/Program Files/Alibaba路径下新建文件夹cloudmonitor。
3.  解压到C:/Program Files/Alibaba/cloudmonitor目录。
4.  使用管理员权限双击运行安装云监控C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/InstallApp-NT.bat。
5.  使用管理员权限双击运行启动云监控C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/StartApp-NT.bat。
6.  安装完成后，可以通过Windows服务面板来查看、启动、停止云监控服务（Cloud Monitor Application）。

**卸载步骤**

1.  使用Windows服务面板停止云监控服务。
2.  通过管理员权限运行C:/Program Files/Alibaba/cloudmonitor/wrapper/bin/UninstallApp-NT.bat来删除云监控服务。
3.  到安装目录删除整个目录C:/Program Files/Alibaba/cloudmonitor。

**无公网下载**

如果没有公网可以通过内网地址下载，例如青岛64位安装包下载地址为：[http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.2/windows64/agent-windows64-1.3.2-package.zip](http://cms-agent-cn-qingdao.oss-cn-qingdao.aliyuncs.com/release/1.3.2/windows64/agent-windows64-1.3.2-package.zip)

-   可以通过修改两处cn-qingdao切换到其他region下载地址
-   可以通过修改两处windows64成windows32来切换到32位版本
-   可以通过修改两处1.3.2切换到其他版本

**Region列表**

|**Region中文名称**|**Region英文表示**|**城市**|
|:-------------|:-------------|:-----|
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

## 资源消耗 {#section_oh3_r3f_xdb .section}

-   安装包: 75M。
-   安装后大小: 200M。
-   内存: 64M。
-   CPU: 1%以下。
-   网络: 使用内网网络，不消耗公网流量。

## 常见问题 {#section_vv2_nff_xdb .section}

-   云监控日志位置
-   -   Linux：/usr/local/cloudmonitor/logs
-   Windows：C:/Program Files/Alibaba/cloudmonitor/logs

-   插件占用的端口和我的业务端口冲突怎么办？

    1.  修改云监控配置来更换端口范围，文件位置：/usr/local/cloudmonitor/wrapper/conf/wrapper.conf
    2.  重启云监控
    ```
    
    wrapper.port.min=40000
    wrapper.port.max=41000
    wrapper.jvm.port.min=41001
    wrapper.jvm.port.max=42000
    ```


