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
from aliyunsdkcore import client
from aliyunsdkcms.request.v20190101 import DescribeMetricListRequest
import time
clt = client.AcsClient('your_access_key','your_access_secret','your_region_id')
request = DescribeMetricListRequest.DescribeMetricListRequest()
request.set_accept_format('json')
request.set_Namespace('acs_ecs_dashboard')
request.set_Metric('CPUUtilization')
start_time = "2016-10-25 10:00:00"
timestamp_start = int(time.mktime(time.strptime(start_time, "%Y-%m-%d %H:%M:%S"))) * 1000
request.set_StartTime(timestamp_start)
request.set_Dimensions("{'instanceId':'i-94g5h****'}")
request.set_Period('60')
result = clt.do_action_with_exception(request)
print result
```

