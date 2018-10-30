# Process Monitoring {#concept_a31_ygc_5db .concept}

By default, process monitoring allows you to collect information about CPU usage, memory usage, and the number of files opened by the active processes in a period of time. If you include a process keyword, the number of processes containing the keyword is collected.

## View the resource consumption of active processes {#section_njq_fdd_xdb .section}

-   The agent filters out the top five processes with the maximum CPU usage every minute, showing their respective CPU usage, memory usage, and the number of files they opened.
-   For the CPU usage and memory usage of the processes, see the Linux top command. CPU usage refers to the usage of a multi-core CPU.
-   For the number of files opened by an active process, see the Linux lsof command.

**Note:** 

-   If your process occupies multiple CPUs, the CPU usage will exceed 100%. The collection result indicates the total usage of multiple CPU cores.
-   If the top five processes are changing over the time span specified for your query, the process list will show all processes that have ever ranked top five over the specified time span. The times in the list indicate when the processes last ranked top five.
-   The CPU usage, memory usage, and number of opened files are collected only for the top five processes. Therefore, if an process has not ranked top five continuously over the time span specified for the query, its data points will appear discontinuous in the monitoring charts. The density of the data points for a process indicates its degree of activity on the server.
    -   As shown in the following figure, the wrapper process has not continuously ranked top five processes with the maximum server CPU usage. Therefore, the data points in the monitoring charts are sparse and discontinuous. Those data points indicate that the process has ranked top five at exactly the points of time.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6151/154088938621153_en-US.png)

    -   The following figure shows the monitoring charts of the java process. The data points in the monitoring charts are dense and continuous. This indicates that the process is continuously ranked top five with the maximum CPU usage.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6151/154088938621166_en-US.png)


## Monitor the number of specified processes {#section_xdd_t2d_xdb .section}

You can know the number and viability status of key processes by monitoring the number of processes.

-   Add process monitoring

    Examples

    For example, the server is running the following processes: `/usr/bin/java -Xmx2300m -Xms2300m org.apache.catalina.startup.Bootstrap` `/usr/bin/ruby` `nginx -c /ect/nginx/nginx.conf` If the user configures six keywords, the output is as follows: Keyword: `ruby`, number of processes collected: 1, hitting a process name. Keyword: `nginx`, number of processes collected: 1, hitting a process name and a parameter. Keyword: `/usr/bin`, number of processes collected: 2, hitting a path \(the path is included in two processes\). Keyword: `apache.catalina`, number of processes collected: 1, hitting some parameters. Keyword: `nginx.conf`, number of processes collected: 1, hitting some parameters. Keyword: `-c`, number of processes collected: 1, hitting some parameters.


**Procedure**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left navigation pane, click **Host Monitoring**.
3.  Click the name of the host you want to monitor, or click **Monitoring Charts** in the actions column to access the host monitoring details page.
4.  Click the **Process Monitoring** tab on the page to switch to the process monitoring page.
5.  On the process count monitoring chart, click **Add Process** to add the process you want to monitor.

-   Delete a monitored process
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left navigation pane, click **Host Monitoring**.
    3.  Click the name of the host you want to monitor, or click **Monitoring Charts** in the actions column to open the host monitoring details page.
    4.  Click the **Process Monitoring** tab on the page to switch to the process monitoring page.
    5.  On the process count monitoring chart, click **Add Process** to show the process list.
    6.  Select the target process and click **Delete**.

-   Set alarm rules

    After you configure monitoring for the specified process, you can configure alarm rules for the process. After that, you can receive an alarm notification when the number of processes changes.

    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left navigation pane, click **Host Monitoring**.
    3.  Select the host for which you want to set process monitoring alarm rules, and then click **Alarm Rules** in the actions column. The Alarm Rules page is displayed.
    4.  Click **Create Alarm Rule** in the upper-right corner of the page to open the alarm rule creating page.
    5.  Select **Total Number of Processes** in the rule description field, and then set an appropriate alarm threshold. If multiple processes are configured on the host, the number of processes varies. You can click **Add Alarm Rule** to configure alarm rules for multiple processes at a time.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6151/154088938621167_en-US.png)


