# Python SDK使用手册 {#concept_ec4_x1p_zdb .concept}

```
需要安装有python2.7版本。
```

## 安装pip {#section_xm1_z1p_zdb .section}

如果已有pip或者使用其他方案，可忽略此步骤。

[如何安装pip](http://pip-cn.readthedocs.org/en/latest/installing.html)

## 安装cms-python-sdk的依赖 {#section_agq_3bp_zdb .section}

```
pip install aliyun-python-sdk-core
pip install aliyun-python-sdk-cms
```

[最新版Python SDK](https://github.com/aliyun/aliyun-openapi-python-sdk/blob/master/aliyun-python-sdk-cms/aliyunsdkcms/request/v20190101/PutCustomMetricRequest.py)

## Code示例 {#section_h0p_jc4_0ug .section}

```
#!/usr/bin/env python
#coding=utf-8

from aliyunsdkcore.client import AcsClient
from aliyunsdkcore.acs_exception.exceptions import ClientException
from aliyunsdkcore.acs_exception.exceptions import ServerException
from aliyunsdkcms.request.v20190101.DescribeMetricListRequest import DescribeMetricListRequest

client = AcsClient('<accessKeyId>', '<accessSecret>', 'cn-beijing')

request = DescribeMetricListRequest()
request.set_accept_format('json')

request.set_StartTime("2019-05-21 10:00:00")
request.set_Dimensions("{\"instanceId\":\"i-2ze3*******\"}")
request.set_Period("60")
request.set_Namespace("acs_ecs_dashboard")
request.set_MetricName("CPUUtilization")

response = client.do_action_with_exception(request)
# python2:  print(response)
print(str(response, encoding='utf-8'))
			
```

