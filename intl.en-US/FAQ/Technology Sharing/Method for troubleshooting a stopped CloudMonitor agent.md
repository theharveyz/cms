# Method for troubleshooting a stopped CloudMonitor agent {#concept_um4_gs4_zdb .concept}

A CloudMonitor agent connects to the server using the heartbeat mechanism at an interval of three minutes. If the CloudMonitor agent fails to respond to a heartbeat for five consecutive times \(that is, within 15 minutes\), the server registers the agent as stopped.

A CloudMonitor agent may have stopped due to the following two reasons:

1.  The agent fails to communicate with the CloudMonitor server.
2.  The CloudMonitor process is ended.

## The agent fails to communicate with the CloudMonitor server {#section_wxf_js4_zdb .section}

If the agent ran normally before the exception occurred, you can reinstall it.

1.  Log on to the [**CloudMonitor console**](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, select **Host Monitoring**. The **Host Monitoring** page is displayed.
3.  Select the target host and click **Batch Install**, or install the agents manually. For details, see [**Install CloudMonitor agent**](https://www.alibabacloud.com/help/faq-detail/38859.htm).

## The CloudMonitor process is ended {#section_ofg_rxj_wfb .section}

You can determine the reason why the agent has stopped by checking the CloudMonitor logs and agent running status to verify whether the CloudMonitor process ended due to a bug in CloudMonitor. To check the logs and agent running status, use the following steps according to your OS. If a bug is suspected as the cause, we recommend that you open a ticket for consultation.

1.  **Check CloudMonitor logs.**
    -   Linux: /usr/local/cloudmonitor/logs
    -   Windows: C:/Program Files/Alibaba/cloudmonitor/logs
2.  **Check the agent running status.**

    -   Linux:

        ```
        sudo /usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh status
        ```

    -   Windows:

        ```
        C:\"Program Files (x86)"\Alibaba\cloudmonitor\wrapper\bin\AppCommand.bat status
        ```

    In Linux, you can run the `/usr/local/cloudmonitor/wrapper/bin/cloudmonitor.sh` command to view additional help information.


