# Python SDK使用手册 {#concept_ec4_x1p_zdb .concept}

```
需要安装有python2.7版本。
```

## 安装pip {#section_xm1_z1p_zdb .section}

如果已有pip或者使用其他方案，可忽略此步骤。

[如何安装pip](http://pip-cn.readthedocs.org/en/latest/installing.html)

## 命令行工具 CLI（如果已安装，请略过）： {#section_ym1_z1p_zdb .section}

```
pip install aliyuncli
pip install -Iv aliyun-python-sdk-cms==5.0.0
aliyuncli configure
```

[命令行工具 CLI 安装说明](https://www.alibabacloud.com/help/doc-detail/43008.htm?spm=a2c63.l28256.a3.5.520d7bd4habdyE)

## 安装cms-python-sdk的依赖 {#section_agq_3bp_zdb .section}

```
pip install aliyun-python-sdk-core
pip install aliyun-python-sdk-cms
```

[最新版Python SDK](https://github.com/aliyun/aliyun-openapi-python-sdk/blob/master/aliyun-python-sdk-cms/aliyunsdkcms/request/v20180308/PutCustomMetricRequest.py)

**code示例**

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

