# Python SDK User Manual {#concept_ec4_x1p_zdb .concept}

This topic is a reference for installing and using the Python SDK.

## Install pip {#section_eb3_chl_bhb .section}

-   You have installed Python v2.7.
-   You have installed pip or an alternative package management system. For more information on pip, see [How to install pip](http://pip-cn.readthedocs.org/en/latest/installing.html).

## Install cms-python-sdk dependencies {#section_agq_3bp_zdb .section}

```
pip install aliyun-python-sdk-core
pip install aliyun-python-sdk-cms
```

[Latest version of Python SDK](https://github.com/aliyun/aliyun-openapi-python-sdk/blob/master/aliyun-python-sdk-cms/aliyunsdkcms/request/v20190101/PutCustomMetricRequest.py)

## Code example {#section_low_jf4_4b7 .section}

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

