# 云监控控制台为什么CPU健康显示为0% {#concept_b1k_nvk_zdb .concept}

该问题通常主要是因为您的CPU使用率很低的缘故，从监控图上看CPU的使用基本在0.5%上下徘徊。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6269/15507175624963_zh-CN.jpg)

而ECS向云监控上报数据是一分钟一次，您在控制台上看到的数据是5分钟的平均值，如果5次上报的平均值都低于0.5就会显示0%的。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6269/15507175624964_zh-CN.jpg)

