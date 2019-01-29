# ECS状态变化事件的自动化运维最佳实践 {#concept_xhk_yq3_pgb .concept}

本文通过实践案例为您介绍云监控如何利用MNS消息队列实现自动化处理ECS状态变化事件。

## 背景信息 {#section_gvb_lr3_pgb .section}

阿里云ECS在已有的系统事件的基础上，通过云监控新发布了状态变化类事件和抢占型实例的中断通知事件。每当ECS实例的状态发生变化的时候，都会触发一条ECS实例状态变化事件。这种变化包括您在控制台/OpenAPI/SDK操作导致的变化，也包括弹性伸缩或欠费等原因而自动触发的变化，还包括因为系统异常而触发的变化。

云监控以前发布的系统事件，主要针对告警后人工介入的场景，而这次新发布的事件属于正常类的信息通知，适合自动化的审计运维等场景。为了自动化处理ECS状态变化事件，云监控提供了两种主要途径：一种是通过函数计算，另一种是通过MNS消息队列。本文将为您介绍利用MNS消息队列自动化处理ECS事件的三种最佳实践。

## 自动化处理ECS状态变化事件的准备工作 {#section_mtd_2s3_pgb .section}

-   **创建消息队列** 
    1.  登录[MNS控制台](https://mns.console.aliyun.com/)。
    2.  在队列列表页面，选择地域，单击右上角的**创建队列**，进入新建队列页面。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/121671/154875716438236_zh-CN.png)

    3.  输入队列的名称（例如“ecs-cms-event”）等信息，单击**确认**即可完成创建消息队列。

-   **创建事件报警规则** 
    1.  登录[云监控控制台](https://cms-intl.console.aliyun.com)。
    2.  单击左侧导航栏中的**事件监控**，进入事件查询页面
    3.  单击**报警规则**页签，然后单击右上角的**创建事件报警**，弹出**创建/修改事件报警**对话框。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/121671/154875716438237_zh-CN.png)

    4.  在**基本信息**区域，填写报警规则名称，例如如“ecs-test-rule”。
    5.  设置**事件报警规则**：选择事件类型为**系统事件**。
        -   产品类型、事件等级、事件名称：**产品类型**选择**云服务器ECS**，**事件类型**选择**StatusNotification**，其余按照实际情况填写。
        -   资源范围：选择**全部资源**时，任何资源发生相关事件，都会按照配置发送通知；选择**应用分组**时，只有指定分组内的资源发生相关事件时，才会发送通知。
    6.  在**报警方式**中，选择**消息队列**，然后选择地域和队列（例如ecs-cms-event）。
    7.  完成以上设置后，单击**确定**按钮即可完成创建事件报警规则。

-   **安装Python依赖** 

    本文所有的代码均使用Python 3.6测试通过，您也可以使用Java等其他编程语言。

    请使用Pypi安装以下Python依赖:

    -   aliyun-python-sdk-core-v3\>=2.12.1
    -   aliyun-python-sdk-ecs\>=4.16.0
    -   aliyun-mns\>=1.1.5

## 自动化处理ECS状态变化事件的实施步骤 {#section_k3g_2s3_pgb .section}

云监控会把云服务器ECS所有的状态变化事件都投递到MNS里面，接下来我们需要通过编写代码从MNS获取消息并进行消息处理。

**实践一：对所有ECS的创建和释放事件进行记录**

目前ECS控制台无法查询已经释放的实例。如果您有查询需求，可以通过ECS状态变化事件把所有ECS的生命周期记录在自己的数据库或者日志里。每当创建ECS时，会首先发送一个Pending事件，每当释放ECS时，会最后发送一个Deleted事件。我们需要对这两种事件进行记录。

1.  编辑一个Conf文件。需包含mns的endpoint（可以登录MNS的控制台，在队列列表页，单击**获取Endpoint**得到）、阿里云的access key和secrect、region id（例如cn-beijing）以及mns queue的名字。

    ```
    class Conf:
        endpoint = 'http://<id>.mns.<region>.aliyuncs.com/'
        access_key = '<access_key>'
        access_key_secret = '<access_key_secrect>'
        region_id = 'cn-beijing'
        queue_name = 'test'
        vsever_group_id = '<your_vserver_group_id>'
    
    ```

2.  使用MNS的SDK编写一个MNS Client用来获取MNS消息。

    ```language-python
    # -*- coding: utf-8 -*-
    import json
    from mns.mns_exception import MNSExceptionBase
    import logging
    from mns.account import Account
    from . import Conf
    
    
    class MNSClient(object):
        def __init__(self):
            self.account =  Account(Conf.endpoint, Conf.access_key, Conf.access_key_secret)
            self.queue_name = Conf.queue_name
            self.listeners = dict()
    
        def regist_listener(self, listener, eventname='Instance:StateChange'):
            if eventname in self.listeners.keys():
                self.listeners.get(eventname).append(listener)
            else:
                self.listeners[eventname] = [listener]
    
        def run(self):
            queue = self.account.get_queue(self.queue_name)
            while True:
                try:
                    message = queue.receive_message(wait_seconds=5)
                    event = json.loads(message.message_body)
                    if event['name'] in self.listeners:
                        for listener in self.listeners.get(event['name']):
                            listener.process(event)
                    queue.delete_message(receipt_handle=message.receipt_handle)
                except MNSExceptionBase as e:
                    if e.type == 'QueueNotExist':
                        logging.error('Queue %s not exist, please create queue before receive message.', self.queue_name)
                    else:
                        logging.error('No Message, continue waiting')
    
    
    class BasicListener(object):
        def process(self, event):
            pass
    
    ```

    上述代码只是对MNS消息进行拉取，调用Listener消费消息之后删除消息，后面的实践也会用到。

3.  注册一个Listener进消费指定事件。这个简单的Listener判断收到Pending和Deleted事件时，打印一行日志。

    ```language-python
     # -*- coding: utf-8 -*-
    import logging
    from .mns_client import BasicListener
    
    
    class ListenerLog(BasicListener):
        def process(self, event):
            state = event['content']['state']
            resource_id = event['content']['resourceId']
            if state == 'Panding':
                logging.info(f'The instance {resource_id} state is {state}')
            elif state == 'Deleted':
                logging.info(f'The instance {resource_id} state is {state}')
    
    ```

    Main函数可以这么写：

    ```
    mns_client = MNSClient()
    
    mns_client.regist_listener(ListenerLog())
    
    mns_client.run()
    ```

    实际生产环境下，可能需要把事件存储在数据库里，或者利用SLS日志服务，方便后期的搜索和审计。


**实践二：ECS的关机自动重启**

在某些场景下，ECS会非预期的关机，您可能需要自动重启已经关机的ECS。

为了实现这一目的，我们复用实践一里面的MNS Client，添加一个新的Listener。当收到Stopped事件的时候，对该ECS执行一个Start命令。

```language-python
# -*- coding: utf-8 -*-
import logging
from aliyunsdkecs.request.v20140526 import StartInstanceRequest
from aliyunsdkcore.client import AcsClient
from .mns_client import BasicListener
from .config import Conf


class ECSClient(object):
    def __init__(self, acs_client):
        self.client = acs_client

    # 启动ECS实例
    def start_instance(self, instance_id):
        logging.info(f'Start instance {instance_id} ...')
        request = StartInstanceRequest.StartInstanceRequest()
        request.set_accept_format('json')
        request.set_InstanceId(instance_id)
        self.client.do_action_with_exception(request)


class ListenerStart(BasicListener):
    def __init__(self):
        acs_client = AcsClient(Conf.access_key, Conf.access_key_secret, Conf.region_id)
        self.ecs_client = ECSClient(acs_client)

    def process(self, event):
        detail = event['content']
        instance_id = detail['resourceId']
        if detail['state'] == 'Stopped':
            self.ecs_client.start_instance(instance_id)

```

在实际生产环境下，执行完Start命令后，可能还需要继续接收后续的Starting/Running/Stopped等事件，再配合计时器和计数器，进行Start成功或失败之后的处理。

**实践三：抢占型实例释放前，自动从SLB移除**

抢占型实例在释放之前五分钟左右，会发出释放告警事件，您可以利用这短暂的时间运行一些业务不中断的逻辑。例如，主动从SLB的后端服务器中去掉这台即将被释放的抢占型实例，而不是被动等待实例释放后SLB的自动处理。

我们还是复用实践一的MNS Client，添加一个新的Listener，当收到抢占型实例的释放告警时，调用SLB的SDK。

```language-python
# -*- coding: utf-8 -*-
from aliyunsdkcore.client import AcsClient
from aliyunsdkcore.request import CommonRequest
from .mns_client import BasicListener
from .config import Conf


class SLBClient(object):
    def __init__(self):
        self.client = AcsClient(Conf.access_key, Conf.access_key_secret, Conf.region_id)
        self.request = CommonRequest()
        self.request.set_method('POST')
        self.request.set_accept_format('json')
        self.request.set_version('2014-05-15')
        self.request.set_domain('slb.aliyuncs.com')
        self.request.add_query_param('RegionId', Conf.region_id)

    def remove_vserver_group_backend_servers(self, vserver_group_id, instance_id):
        self.request.set_action_name('RemoveVServerGroupBackendServers')
        self.request.add_query_param('VServerGroupId', vserver_group_id)
        self.request.add_query_param('BackendServers',
                                     "[{'ServerId':'" + instance_id + "','Port':'80','Weight':'100'}]")
        response = self.client.do_action_with_exception(self.request)
        return str(response, encoding='utf-8')


class ListenerSLB(BasicListener):
    def __init__(self, vsever_group_id):
        self.slb_caller = SLBClient()
        self.vsever_group_id = Conf.vsever_group_id

    def process(self, event):
        detail = event['content']
        instance_id = detail['instanceId']
        if detail['action'] == 'delete':
            self.slb_caller.remove_vserver_group_backend_servers(self.vsever_group_id, instance_id)

```

**说明：** 

抢占型实例释放告警的event name与前面不同，应该是“Instance:PreemptibleInstanceInterruption”， mns\_client.regist\_listener\(ListenerSLB\(Conf.vsever\_group\_id\)， 'Instance:PreemptibleInstanceInterruption'\)

在实际生产环境下，您可能需要再申请一台新的抢占型实例，挂载到SLB上，来保证服务能力。

