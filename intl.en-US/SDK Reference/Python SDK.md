# Python SDK {#concept_ec4_x1p_zdb .concept}

This topic is a reference for installing and using the Python SDK.

## Install Python SDK {#section_eb3_chl_bhb .section}

-   You have installed Python v2.7.
-   You have installed pip or an alternative package management system. For more information on pip, see [How to install pip](http://pip-cn.readthedocs.org/en/latest/installing.html).
-   You have installed the Python CLI. For more information, see [How to install CLI](https://partners-intl.aliyun.com/help/doc-detail/43008.htm).

## Use Python SDK {#section_agq_3bp_zdb .section}

```
pip install aliyun-python-sdk-core
pip install aliyun-python-sdk-cms
```

[Latest version of Python SDK](https://github.com/aliyun/aliyun-openapi-python-sdk/blob/master/aliyun-python-sdk-cms/aliyunsdkcms/request/v20180308/PutCustomMetricRequest.py)

**Code example**

```
from aliyunsdkcore import client
from aliyunsdkcms.request.v20190101 import QueryMetricListRequest
import time
clt = client.AcsClient('your_access_key','your_access_secret','your_region_id')
request = QueryMetricListRequest.QueryMetricListRequest()
request.set_accept_format('json')
request.set_Project('acs_ecs_dashboard')
request.set_Metric('CPUUtilization')
start_time = "2016-10-25 10:00:00"
timestamp_start = int(time.mktime(time.strptime(start_time, "%Y-%m-%d %H:%M:%S"))) * 1000
request.set_StartTime(timestamp_start)
request.set_Dimensions("{'instanceId':'i-94g5h****'}")
request.set_Period('60')
result = clt.do_action_with_exception(request)
print result
```

