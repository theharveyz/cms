# How is memory usage calculated in CloudMonitor? {#concept_vmk_tn4_zdb .concept}

Memory usage is calculated using the following formula in CloudMonitor:

\(mem\_total - \(mem\_free + mem\_buffer + mem\_cache\)\)/mem\_total

You can run the `cat /proc/meminfo` command to check mem\_free, mem\_buffer, and mem\_cache. Consider the following example:

```
[root@localhost ~]# cat /proc/meminfo MemTotal: 8011936 kBMemFree: 227336 kBBuffers: 277872 kBCached: 1451828 kB
```

For this example, memory is calculated with the following formula:

\(8011936 - \(227336 + 277872 + 1451828\)\)/8011936

The result of this calculation is that memory usage is about 75%.

