# How to install a CloudMonitor agent on multiple instances using PSSH? {#concept_wgb_kwk_zdb .concept}

PSSH is a Python-based application that allows you to execute SSH commands on up to 30 instances all at once. As such, you will be able to install software, kill a process, or download a file on multiple instances at the same time.

## Install CloudMonitor Agent on a single instance {#section_kts_nwk_zdb .section}

`**bash**-c "$(curl http://cloudmonitor-agent.oss-cn-hangzhou.aliyuncs.com/release/install.sh)"`

## Install CloudMonitor Agent on multiple instances using PSSH {#section_cwj_5wk_zdb .section}

-   Install PSSH.
    1.  Install Python v2.4 or later.
    2.  Install PSSH.

        ```
         wget https://pypi.python.org/packages/source/p/pssh/pssh-2.3.1.tar.gz
         tar zxf pssh-2.3.1.tar.gz
         cd pssh-2.3.1
         python setup.py install 
        
        ```

-   Configure the IP list and prepare the instances on which CloudMonitor will be installed.
    1.  Configure the ip.txt file.
    2.  The format is user@ip:port, one per line. By default, Port 22 is used if you do not specify a different port.
    3.  The sudo permission is required for running commands.
    4.  The password used for multiple instances must be the same for each instance. Alternatively, you can establish password-less SSH trust between instances.
-   Execute parallel commands on multiple instances.

    `pssh -h ip.txt -A -i bash -c "$(curl http://cloudmonitor-agent.oss-cn-hangzhou.aliyuncs.com/release/install.sh)"`

    -H: Enter the host list file.

    -A: Enter the password you have set for the corresponding instances. If you established password-less SSH trust between instances, you do not need to enter this parameter.

    -I: Enter your command.

-   Check whether CloudMonitor is installed.

    `pssh -h ip.txt -A -i"/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh status"`


