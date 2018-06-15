# 利用pssh批量安装云监控Agent {#concept_wgb_kwk_zdb .concept}

## pssh介绍 {#section_o3f_nwk_zdb .section}

pssh 是一个python写的批量执行工具,非常适合30台服务器以内的一些重复性的操作。例如安装一个软件，kill 一个进程，下载文件等。

## 单机安装云监控Agent {#section_kts_nwk_zdb .section}

`**bash**-c "$(curl http://cloudmonitor-agent.oss-cn-hangzhou.aliyuncs.com/release/install.sh)"`

## pssh批量安装云监控Agent {#section_cwj_5wk_zdb .section}

-   安装pssh

    1.  安装 python 2.4 以上
    2.  安装 pssh

        ```
         wget https://pypi.python.org/packages/source/p/pssh/pssh-2.3.1.tar.gz
         tar zxf pssh-2.3.1.tar.gz
         cd pssh-2.3.1
         python setup.py install 
        
        ```

-   配置IP列表,准备安装云监控的机器

    1.  配置ip.txt文件
    2.  格式为user@ip:port每行一个,port不填默认为22
    3.  执行命令的用户需要有sudo权限
    4.  批量安装的机器，密码要相同, 也可以配置无密码互信
-   批量执行

    `pssh -h ip.txt -A -i bash -c "$(curl http://cloudmonitor-agent.oss-cn-hangzhou.aliyuncs.com/release/install.sh)"`

    -h host列表文件

    -A 手工输入密码，无密码互信不需要这个参数

    -i 执行的命令

-   查看云监控是否安装成功

    `pssh -h ip.txt -A -i"/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh status"`


