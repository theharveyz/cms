# Java SDK使用手册 {#concept_llz_kz4_zdb .concept}

## SDK安装 {#section_vlh_lz4_zdb .section}

通过maven进行安装，需要添加的依赖如下：

```
<dependencies>
     <dependency>
       <groupId>com.aliyun</groupId>
       <artifactId>aliyun-java-sdk-core</artifactId>
       <version>3.2.6</version>
    </dependency>
<dependency>
  <groupId>com.aliyun</groupId>
  <artifactId>aliyun-java-sdk-cms</artifactId>
  <version>5.0.4</version>
</dependency>
</dependencies>
```

## SDK下载 {#section_t5g_5z4_zdb .section}

Github下载地址：[https://github.com/aliyun/aliyun-openapi-java-sdk/tree/master/aliyun-java-sdk-cms](https://github.com/aliyun/aliyun-openapi-java-sdk/tree/master/aliyun-java-sdk-cms)

## 测试代码 {#section_yyd_dn1_f2b .section}

-   查询监控数据
    -   请求示例

        使用时请将如下示例中的accessKey和accessSecret替换成您的Access Key。

        ```
        package com.aliyuncs.cms.test;
        import com.alibaba.fastjson.JSONObject;
        import com.aliyuncs.DefaultAcsClient;
        import com.aliyuncs.IAcsClient;
        import com.aliyuncs.cms.model.v20170301.QueryMetricListRequest;
        import com.aliyuncs.cms.model.v20170301.QueryMetricListResponse;
        import com.aliyuncs.exceptions.ClientException;
        import com.aliyuncs.exceptions.ServerException;
        import com.aliyuncs.http.FormatType;
        import com.aliyuncs.profile.DefaultProfile;
        import com.aliyuncs.profile.IClientProfile;
        public class QueryMetricListDemo {
            public static void main(String[] args) {
                QueryMetricListRequest request = new QueryMetricListRequest();
                request.setProject("acs_ecs_dashboard");
                request.setMetric("cpu_idle");
                request.setPeriod("60");
                request.setStartTime("2017-03-14 14:20:27");
                request.setEndTime("2017-03-14 14:30:27");
                JSONObject dim = new JSONObject();
                dim.put("instanceId", "<your_instanceId>");
                request.setDimensions(dim.toJSONString());
                request.setAcceptFormat(FormatType.JSON);
                IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou",
                        "<your_access_key_id>", "<your_access_key_secret>");
                IAcsClient client = new DefaultAcsClient(profile);
                try {
                    QueryMetricListResponse response = client.getAcsResponse(request);
                    System.out.println(response.getCode());
                    System.out.println(response.getMessage());
                    System.out.println(response.getRequestId());
                    System.out.println(response.getDatapoints());
                } catch (ServerException e) {
                    e.printStackTrace();
                } catch (ClientException e) {
                    e.printStackTrace();
                }
            }
        }
        ```

    -   返回示例

        ```
        Code:200
        Message:null
        RequestId:727B48BD-55E3-4E5D-BEF4-1D092055F7A4
        Datapoints:[
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":94.62,
                "userId":"1270676679546704",
                "timestamp":1489472460000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":95.11,
                "userId":"1270676679546704",
                "timestamp":1489472520000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":95.16,
                "userId":"1270676679546704",
                "timestamp":1489472580000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":94.69,
                "userId":"1270676679546704",
                "timestamp":1489472640000
            },
            {
                "Maximum":100,
                "Minimum":20,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":95.82,
                "userId":"1270676679546704",
                "timestamp":1489472700000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":94.77,
                "userId":"1270676679546704",
                "timestamp":1489472760000
            },
            {
                "Maximum":100,
                "Minimum":33.33,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":95.18,
                "userId":"1270676679546704",
                "timestamp":1489472820000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":95.11,
                "userId":"1270676679546704",
                "timestamp":1489472880000
            },
            {
                "Maximum":100,
                "Minimum":20,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":94.5,
                "userId":"1270676679546704",
                "timestamp":1489472940000
            },
            {
                "Maximum":100,
                "Minimum":20,
                "instanceId":"i-bp18abl200xk9599ck7c",
                "Average":94.99,
                "userId":"1270676679546704",
                "timestamp":1489473000000
            }
        ]
        }
        ```

-   创建报警规则
    -   请求示例

        ```
        package com.aliyuncs.cms.test;
        import com.alibaba.fastjson.JSONArray;
        import com.alibaba.fastjson.JSONObject;
        import com.aliyuncs.DefaultAcsClient;
        import com.aliyuncs.IAcsClient;
        import com.aliyuncs.cms.model.v20170301.CreateAlarmRequest;
        import com.aliyuncs.cms.model.v20170301.CreateAlarmResponse;
        import com.aliyuncs.exceptions.ClientException;
        import com.aliyuncs.exceptions.ServerException;
        import com.aliyuncs.http.FormatType;
        import com.aliyuncs.profile.DefaultProfile;
        import com.aliyuncs.profile.IClientProfile;
        public class CreateAlarmDemo {
            public static void main(String[] args) {
                CreateAlarmRequest request = new CreateAlarmRequest();
                request.setName("create_alarm_test");
                request.setNamespace("acs_ecs_dashboard");
                request.setMetricName("vm.MemoryUtilization");
                JSONArray dimensions = new JSONArray();
                JSONObject dim = new JSONObject();
                dim.put("userId", "<your_userId>");
                dim.put("instanceId", "<your_instanceId>");
                dimensions.add(dim);
                request.setDimensions(dimensions.toJSONString());
                request.setPeriod(900);
                request.setStatistics("Average");
                request.setComparisonOperator(">=");
                request.setThreshold("35");
                request.setEvaluationCount(2);
                JSONArray contactGroups = new JSONArray();
                contactGroups.add("<your_group1>");
                contactGroups.add("<your_group2>");
                request.setContactGroups(contactGroups.toJSONString());
                request.setStartTime(6);
                request.setEndTime(20);
                request.setNotifyType(1);
                request.setAcceptFormat(FormatType.JSON);
                IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou",
                        "<your_access_key_id>", "<your_access_key_secret>");
                IAcsClient client = new DefaultAcsClient(profile);
                try {
                    CreateAlarmResponse response = client.getAcsResponse(request);
                    System.out.println(response.getCode());
                    System.out.println(response.getMessage());
                    System.out.println(response.getRequestId());
                    System.out.println(response.getData());
                } catch (ServerException e) {
                    e.printStackTrace();
                } catch (ClientException e) {
                    e.printStackTrace();
                }
            }
        }
        ```

    -   返回示例

        ```
        Code:200
        Message:null
        RequestId:B8E6E26A-9435-4D52-8796-68793935CA74
        Data:81b412bf-fbbb-4a40-8d74-b68ec849a091
        ```


