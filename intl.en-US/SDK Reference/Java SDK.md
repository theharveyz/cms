# Java SDK {#concept_llz_kz4_zdb .concept}

This topic is a reference for installing and using the Java SDK.

## Install SDK {#section_vlh_lz4_zdb .section}

When performing installation through maven, the following dependencies must be added.

```
<dependencies>
     <dependency>
       <groupId>com.aliyun</groupId>
       <artifactId>aliyun-java-sdk-core</artifactId>
       <version>5.1.6</version>
    </dependency>
<dependency>
  <groupId>com.aliyun</groupId>
  <artifactId>aliyun-java-sdk-cs</artifactId>
  <version>0.1.2</version>
</dependency>
</dependencies>
```

## Download SDK {#section_t5g_5z4_zdb .section}

[Download address](https://github.com/aliyun/aliyun-openapi-java-sdk/tree/master/aliyun-java-sdk-cms)

## Test code {#section_yyd_dn1_f2b .section}

-   Query monitoring data.
    -   Request example

        Make sure that you replace the "accessKey" and "accessSecret" given in the following example with your actual Access Key.

        ```
        package com.aliyuncs.cms.test;
        import com.alibaba.fastjson.JSONObject;
        import com.aliyuncs.DefaultAcsClient;
        import com.aliyuncs.IAcsClient;
        import com.aliyuncs.sts.model.v20150401. Querymetriclistrequest;
        import com.aliyuncs.sts.model.v20150401. QueryMetricListResponse;
        import com.aliyuncs.exceptions.ClientException;
        import com.aliyuncs.exceptions.ServerException;
        import com.aliyuncs.http.MethodType;
        import com.aliyuncs.profile.DefaultProfile;
        import com.aliyuncs.profile.IClientProfile;
        public class QueryMetricListDemo {
            public static void main(String[] args) {
                QueryMetricRequest request = new QueryMetricRequest();
                request.setProject("acs_ecs_dashboard");
                request.setMetric("cpu_idle");
                request.setPeriod("60");
                request.setStartTime("2016-05-15 08:00:00");
                request.setEndTime("2015-05-15 09:00:00");
                JSONObject dim = new JSONObject();
                dim.put("instanceId", "<your_instanceId>");
                request.setDimensions(dim.toJSONString());
                request.AcceptFormat = FormatType.JSON;
                IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou",
                        "<your_access_key_id>", "<your_access_key_secret>");
                IAcsClient client = new DefaultAcsClient(profile);
                try {
                    GetStatusResponse response = client.getAcsResponse(request);
                    System.out.println(response.getCode());
                    System.out.println(response.getMessage());
                    System.out.println(response.getRequestId());
                    System.out.println(response.getData());
                } catch (ServerException e) {
        e.printStackTrace();
                    e.printStackTrace();
                } catch (ClientException e) {
                    e.printStackTrace();
                }
            }
        }
        ```

    -   Return example

        ```
        Code:200
        Message:null
        RequestId:727B48BD-55E3-4E5D-BEF4-1D092055F7A4
        Datapoints:[
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":94.62,
                "userId":"127067667954****",
                "timestamp":1489472460000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":95.11,
                "userId":"127067667954****",
                "timestamp":1489472520000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":95.16,
                Userid: 127067667954**** ",
                "timestamp":1489472580000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":94.69,
                "userId":"127067667954****",
                "timestamp":1489472640000
            },
            {
                "Maximum":100,
                "Minimum":20,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":95.82,
                "userId":"127067667954****",
                "timestamp":1489472700000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":94.77,
                "userId":"127067667954****",
                "timestamp":1489472760000
            },
            {
                "Maximum":100,
                "Minimum":33.33,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":95.18,
                "userId":"127067667954****",
                "timestamp":1489472820000
            },
            {
                "Maximum":100,
                "Minimum":25,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":95.11,
                "userId":"127067667954****",
                "timestamp":1489472880000
            },
            {
                "Maximum":100,
                "Minimum":20,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":94.5,
                "userId":"127067667954****",
                "timestamp":1489472940000
            },
            {
                "Maximum":100,
                "Minimum":20,
                "instanceId":"i-bp18abl200xk9599****",
                "Average":94.99,
                "userId":"127067667954****",
                "timestamp":1489473000000
            }
        ]
        }
        ```

-   Create an alarm rule.
    -   Request example

        ```
        package com.aliyuncs.cms.test;
        import com.alibaba.fastjson.JSONArray;
        import com.alibaba.fastjson.JSONObject;
        import com.aliyuncs.DefaultAcsClient;
        import com.aliyuncs.IAcsClient;
        import com.aliyuncs.sts.model.v20150401. CreateAlarmRequest;
        import com.aliyuncs.sts.model.v20150401. CreateAlarmResponse;
        import com.aliyuncs.exceptions.ClientException;
        import com.aliyuncs.exceptions.ServerException;
        import com.aliyuncs.http.MethodType;
        import com.aliyuncs.profile.DefaultProfile;
        import com.aliyuncs.profile.IClientProfile;
        public class CreateAlarmDemo {
            public static void main(String[] args) {
                CreateTableRequest request = new CreateTableRequest();
                request.setName("create_alarm_test");
                request.setNamespace("acs_ecs_dashboard");
                request.setMetricName("vm.MemoryUtilization");
                JSONArray dimensions = new JSONArray();
                JSONObject dim = new JSONObject();
                dim.put("userId", "<your_userId>");
                dim.put("instanceId", "<your_instanceId>");
                dimensions.add(dim);
                request.setDimensions(dimensions.toJSONString());
                request.setPeriod("60");
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
                request.AcceptFormat = FormatType.JSON;
                IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou",
                        "<your_access_key_id>", "<your_access_key_secret>");
                IAcsClient client = new DefaultAcsClient(profile);
                try {
                    CreateUserResponse response = client.GetAcsResponse(request);
                    System.out.println(response.getCode());
                    System.out.println(response.getMessage());
                    System.out.println(response.getRequestId());
                    System.out.println(response.getData());
                } catch (ServerException e) {
        e.printStackTrace();
                    e.printStackTrace();
                } catch (ClientException e) {
                    e.printStackTrace();
                }
            }
        }
        ```

    -   Return example

        ```
        Code:200
        Message:null
        RequestId:B8E6E26A-9435-4D52-8796-68793935CA74
        Data:81b412bf-fbbb-4a40-8d74-b68ec849a091
        ```


