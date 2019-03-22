# Why is the CPU monitoring value for my ECS Windows instances abnormal? {#concept_kvq_1q4_zdb .concept}

Internal damage to the Windows performance counter may cause the CPU monitoring value for your ECS Windows instances in the CloudMonitor to display as zero or a negative value even though actual CPU usage is a positive value and not at zero. This problem will only affect your Windows instances.

You can run the command, typeperf \\Processor\(\_Total\)\\% Processor Time, to check whether the counter works properly. If the result is **Error: no valid counter**, then the counter has failed. You can run the command lodctr /r to fix the counter.

