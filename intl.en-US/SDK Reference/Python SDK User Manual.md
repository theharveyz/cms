# Python SDK User Manual {#concept_ec4_x1p_zdb .concept}

```
You must have Python 2.7 installed.
```

## Install pip {#section_xm1_z1p_zdb .section}

Skip this step if you already have pip or an alternative.

[How to install pip](http://pip-cn.readthedocs.org/en/latest/installing.html)

## CLI \(skip this step if it has been installed\): {#section_ym1_z1p_zdb .section}

```
pip install aliyuncli
pip install -Iv aliyun-python-sdk-cms==5.0.0
aliyuncli configure
```

[How to install CLI](https://www.alibabacloud.com/help/doc-detail/43008.htm)

## Dependencies for installing cms-python-sdk: {#section_agq_3bp_zdb .section}

```
pip install aliyun-python-sdk-core
pip install aliyun-python-sdk-cms
```

[Latest version of Python SDK](https://github.com/aliyun/aliyun-openapi-python-sdk/blob/master/aliyun-python-sdk-cms/aliyunsdkcms/request/v20180308/PutCustomMetricRequest.py)

**Code example:**

```
from aliyunsdkcore import client
from aliyunsdkcms.request.v20180308 import QueryMetricListRequest
import time
clt = client.AcsClient('your_access_key','your_access_secret','your_region_id')
request = QueryMetricListRequest.QueryMetricListRequest()
request.set_accept_format('json')
request.set_Project('acs_ecs_dashboard')
request.set_Metric('CPUUtilization')
start_time = "2016-10-25 10:00:00"
timestamp_start = int(time.mktime(time.strptime(start_time, "%Y-%m-%d %H:%M:%S"))) * 1000
request.set_StartTime(timestamp_start)
request.set_Dimensions("{'instanceId':'i-94g5hc378'}")
request.set_Period('60')
result = clt.do_action_with_exception(request)
print result
```

