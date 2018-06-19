# Node.js SDK使用手册 {#concept_dc1_qbp_zdb .concept}

```
安装[nodejs](https://docs.npmjs.com/getting-started/installing-node?spm=a2c4g.11186623.2.4.DOdYv1) 和 npm。
```

**示例代码**

```
var Metrics = require("aliyun-metrics")

var client=new Metrics({
        accesskeyId: "your_accesskey_id",
        accesskeySecret: "your_accesskey_secret"
})

client.queryData({
        project:"acs_rds",
        metric:"CpuUsage",
        period:300,
        startTime:"2016-03-08T07:20:00Z",
        endTime:"2016-03-08T09:20:00Z",
        dimensions:"{instanceId:'your_instanceId'}"
}, function(error, data){
        if (error)
                console.log(error)
        else if (!data)
                console.log("data is null")
        else
                console.log(data)
});
```

