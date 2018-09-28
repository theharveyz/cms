# Process Monitoring {#concept_a31_ygc_5db .concept}

Process monitoring by default, allows you to collect information regarding CPU and memory usage and the number of files opened by the active processes over a period of time.  If you include a process keyword, the number of processes containing that keyword are displayed.

## View the consumption status of an active process {#section_njq_fdd_xdb .section}

-   Every minute the agent singles out the top 5 processes with maximum CPU consumption that happens during the last minute. It displays information like CPU usage, memory usage and the number of opened files.

-   For the CPU and memory usage process, see the Linux top command. Here, CPU means a multi-core CPU. CPU means a multi-core CPU.

-   For the number of files opened by an active process, see the Linux lsof command.


**Note:** 

-   If your process occupies multiple CPUs, there will be more than 100% CPU usage. Here the result of the acquisition is the total utilization of multi-core.

-   If the top 5 processes are changing over the time span specified for your query, the process list shows all the processes that are ranked in the top 5 list during the specified time period. The time displayed in the bar chart indicates the processes that were ranked last  among the top 5.Top5 time.

-   Information regarding the CPU and memory usage and the number of files the processes open is collected only for the top 5 processes. If a process is not ranked among the top 5 continually for a longer time specified for any query,  its data points appear randomly in the monitoring charts. The density of the data points for the process shows its degree of activity on the server.

    -   The following charts display the HTTP process, which is not ranked continuously among the top 5  processes with maximum server CPU consumption, the data points in the metric charts appear sparse and not continuous. The data points here indicate that the process has ranked amongst the top 5 at exactly the points of time for the data points.

        ![](images/3354_en-US.png)

    -   The following charts display the mysql process. The data points in the metric charts are dense and appear to be consistent. This indicates that the process is ranked continuously among the top 5 with the maximum CPU consumption.

        ![](images/3356_en-US.png)


## Manage the number of specified processes {#section_xdd_t2d_xdb .section}

You can get the number of key processes and the viability status, through the process count metric.

-   Add a specified process to the monitor

    Example

    For example, the server is currently running the following processes.  `/usr/bin/java -Xmx2300m -Xms2300m org.apache.catalina.startup.Bootstrap` `/usr/bin/ruby` `nginx -c /ect/nginx/nginx.conf`Assume that the user configures 6 keywords, following is the output shown respectively: Keyword: ruby, number of processes returned: 1, hitting a process name. Keyword: nginx, number of processes returned: 1, hitting a process name and a parameter. Keyword: /usr/bin, number of processes returned: 2, hitting 2 paths \(two processes under the paths respectively\). Keyword: apache.catalina, number of processes returned: 1, hitting part of a parameter. Keyword: nginx.conf, number of processes returned: 1, hitting part of a parameter. Keyword: -c, number of processes returned: 1, hitting part of a parameter.


**Procedure**

1.   Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/hostmonitor/host).
2.  Click **Host Monitoring**in the navigation pane.
3.  Click the name of the instance you want to monitor. Or click **Monitoring Chart**from the Actions column to access the instance monitoring details page.
4.  Click Process Monitoring at the top of the page to access process monitoring page.
5.  To add the process you want to monitor, click Add Process button, and enter the Process Name in the search box.

-   Delete a monitored process
    1.   Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/hostmonitor/host).
    2.  Click **Host Monitoring**in the navigation pane.
    3.  Click the name of the instance you want to monitor. Or click **Monitoring Chart**from the Actions column to access the instance monitoring details page.
    4.  Click **Process Monitoring** at the top of the page to access process monitoring page.
    5.  When hovering over the process count monitoring chart, click **Add Process to Monitor** button to access the list of processes added to the page.
    6.  If you want to delete any process, select the process and click Delete.

-   Set alarm rules

    After you have configured monitoring for the specified process, you can configure the alarm rules for the process, you receive an alarm notification when the number of processes changes.

    1.   Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/hostmonitor/host).
    2.  Click **Host Monitoring**in the navigation pane.
    3.  Select the machine that needs to add the alarm that the process monitors, and click the alarm rule in action, enter the alarm Rules Page.
    4.  Click new alarm rule at the top of the page to enter the alarm rule creation page.
    5.  Select the number of processes in the rule description, and then configure the appropriate alarm threshold. If multiple processes are configured on the machine, the number of processes varies, you can click Add alarm rule to configure alerts for multiple processes at once.
    ![](images/3367_en-US.png)


