# Node.js SDK User Manual {#concept_dc1_qbp_zdb .concept}

```
Install Node.js and npm
```

**Code example**

```
VaR metrics = require ("aliyun-metrics ")

VaR client = new metrics ({
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
        else if (! data)
                console.log("data is null")
        else
                console.log(data)
});
```

