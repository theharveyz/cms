# 报警信息写入消息服务 MNS {#concept_270417 .concept}

本文为您介绍如何将阈值类指标的报警信息写入到指定的消息服务 MNS。

## 操作步骤 {#section_761_9fe_yie .section}

1.  授权云监控将报警信息写入消息服务 MNS的权限，单击[这里](https://ram.console.aliyun.com/#/role/authorize?request=%7B%22Requests%22:%20%7B%22request1%22:%20%7B%22RoleName%22:%20%22AliyunCloudMonitorDefaultRole%22,%20%22TemplateId%22:%20%22DefaultRole%22%7D%7D,%20%22ReturnUrl%22:%20%22http:%2F%2Fcms.console.aliyun.com%2F%23%2Feventsubscription%2Ffault%22,%20%22Service%22:%20%22CloudMonitor%22%7D)进行授权。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223330/155860287947776_zh-CN.png)

2.  通过阿里云 OpenAPI Explorer 调用[PutResourceMetricRule](https://api.aliyun.com/#/?product=Cms&api=PutResourceMetricRule)接口，创建报警规则。
3.  调用[PutMetricRuleTargets](https://api.aliyun.com/#/?product=Cms&api=PutMetricRuleTargets)接口，创建一个指定报警规则的报警信息，并写入指定MNS的配置。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223330/155860287947778_zh-CN.png)

    ARN：指具体写入的MNS queue或topic，写入queue的ARN格式为`"acs:mns:{$RegionId}:{$UserId}:/queues/{$queueName}/messages"`，写入topic的ARN格式为`"acs:mns:{$RegionId}:{$UserId}:/topics/{$queueName}/messages"`。


PutMetricRuleTargets接口参数示例：

``` {#codeblock_swx_s3f_ada}
RuleId:"db17-4afc-b11a-568512d5a1f9",
Targets:[{
    Id: 1,
    Arn:"acs:mns:{$RegionId}:{$UserId}:/queues/{$queueName}/messages",
    Level: ["INFO", "WARN", "CRITICAL"],
}]
```

## 写入消息服务 MNS 的消息体说明 {#section_1dk_rll_qal .section}

写入MNS的MessageBody为JSON String，从MNS消费到MessageBody后，请按JSON字符串来解析，消息结构如下：

``` {#codeblock_8d1_wso_1p1 .language-json}
{
  "ruleId": "putNewAlarm_group_778af9ba-a291-46ab-ac53-3983bcee****",
  "ruleName": "test",
  //当前Level
  "curLevel": "WARN",
  //前一级别
  "preLevel": "OK",
  //触发本次报警的实例
  "resources": "{\"instanceId\": \"i-uf61rfofjd2iku7e****\"}",
  //触发本次报警的条件
  "escalation": {
    "comparisonOperator": "GreaterThanYesterday",
    "level": 3,
    "statistics": "Average",
    "tag": "WARN",
    "threshold": "0",
    "times": 1
  },
  "metricData": {
    "timestamp": 1534736160000,
    "userId": "127067667954****",
    "instanceId": "i-uf61rfofjd2iku7e****",
    "Average": 470687744,
    "Maximum": 470794240,
    "Minimum": 470556672,
    //环比同比相关参数--开始
    "AliyunCmsPrevValues": { //对比的数据
      "timestamp": 1534649760000,
      "userId": "127067667954****",
      "instanceId": "i-uf61rfofjd2iku7e****",
      "Average": 468463616,
      "Maximum": 468549632,
      "Minimum": 468258816
    },
    //对比计算的公式
    "AliyunCmsComplexExpression": "100.0 * ($Average-$$prevAverage)/$$prevAverage",
    //对比计算的换算式
    "AliyunCmsComplexMath": "100.0 * (470687744-468463616)/468463616",
    //对比计算的结果
    "AliyunCmsComplexValue": 0.47477070236336133
    //环比同比相关参数--结束
  },
  //metric信息
  "metricName": "memory_actualusedspace#60",
  "namespace": "acs_ecs_dashboard",
  "period": "60",

  //应用分组信息
  "groupBy": "group",
  "productGroupName": "RDS实例组",
  "groupId":"44958",

  //报警时间
  "lastTime": 327362743, //持续时间
  "time": 1534736160000, //数据发生时间

  "userId": "173651113438****",
  "eventName": "AlertOk",
  "eventType": "Alert",
  //用来trace消息
  "batchId": "4272653-152082****-0",
  "version": "1.0"
}
```

