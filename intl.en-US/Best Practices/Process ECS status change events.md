# Process ECS status change events {#concept_xhk_yq3_pgb .concept}

This topic describes how CloudMonitor automatically processes ECS status change events by using MNS message queues.

## Overview {#section_gvb_lr3_pgb .section}

An ECS instance status change event is triggered when the instance status changes. Specifically, a status change event can indicate changes resulting from operations on the console, the usage of APIs or SDKs, automatic scaling, detection of overdue payments, system exceptions, and more.

To automate the processing of ECS status change events, CloudMonitor provides two methods: function calculation formulas and MNS message queues. This topic describes three best practice cases that use MNS message queues.

## Preparations {#section_mtd_2s3_pgb .section}

-   **Create a message queue.** 
    1.  Log on to the [MNS Console](https://partners-intl.console.aliyun.com/#/mns).
    2.  On the Queue List page, select the target region, and click **Create Queue** in the upper-right corner.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/121671/155064626238236_en-US.png)

    3.  In the New Queue dialog box, enter the queue name \(for example, ecs-cms-event\) and other required information, and then click **OK**.

-   **Create an alarm rule for status change events.** 
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, click **Event Monitoring**.
    3.  Switch to the Alarm Rules tab page, and then click **Create Event Alerts**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/121671/155064626238237_en-US.png)

    4.  In the **Basic Information** area, enter a name for the alarm rule, for example, ecs-test-rule.
    5.  In the **Event alert** area, set the parameters as follows:
        -   Set **Event Type** to **System Event**.
        -   Set **Product Type** to **ECS** and **Event Type** to **StatusNotiifcation**, and set other parameters as needed.
        -   If **Resource Range** is set to **All Resources**, change events of any resource will trigger notifications. If **Resource Range** is set to **Application Groups**, only change events of the resources within the specified group will trigger notifications.
    6.  In the **Alarm Type** area, select **MNS queue**, and then specify **Region** and **Queue** \(for example, ecs-cms-event\).
    7.  Click **OK**.

-   **Install Python dependencies.** 

    The following code is tested in Python 3.6. You can use other programming languages, such as Java, as needed.

    Use PyPi to install the following Python dependencies:

    -   aliyun-python-sdk-core-v3 of 2.12.1 or later
    -   aliyun-python-sdk-ecs of 4.16.0 or later
    -   aliyun-mns of 1.1.5 or later

## Procedure {#section_k3g_2s3_pgb .section}

CloudMonitor sends all status change events of ECS instances to MNS. You can then obtain the notifications from MNS and process them by running code. The following practice sections overview a complete tutorial of the preceding methods.

**Practice 1: Records of all ECS creation and release events**

Currently, you cannot query instances that have been released on the ECS console. If you need to perform these queries, you need to record the life cycle of all ECS instances in your own database or log through an ECS status change event. Specifically, whenever an ECS instance is created, a Pending event will be sent, and whenever an ECS instance is released, a Deleted event will be sent. You can record these two events by performing the following steps:

1.  Create a Conf file, which must include the MNS endpoint, AccessKeyId and AccessKeySecret of your Alibaba Cloud account, region ID \(for example, cn-beijing\), and the MNS queue name.

    **Note:** To view the MNS endpoint, you can log on to the MNS console, and click **Get Endpoint** on the Queue List page.

    ```
    class Conf:
        endpoint = 'http://<id>.mns.<region>.aliyuncs.com/'
        access_key = '<access_key>'
        access_key_secret = '<access_key_secrect>'
        region_id = 'cn-beijing'
        queue_name = 'test'
        vsever_group_id = '<your_vserver_group_id>'
    
    ```

2.  Use the MNS SDK to compile an MNS client to receive MNS messages.

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

    The preceding code is used only to pull MNS messages and delete the messages after the listener consumption message is called.

3.  Register a listener to use a specified event. When this listener determines that it has received a Pending or Deleted event, it prints a row in the log file.

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

    The following Main function can also be used:

    ```
    mns_client = MNSClient()
    
    mns_client.regist_listener(ListenerLog())
    
    mns_client.run()
    ```

    In your actual scenario, you can store events in your database or use SLS to facilitate search and audit tasks at a later date.


**Practice 2: Automatic restart of ECS servers**

In some scenarios, ECS servers may shut down unexpectedly. In this case, you need to set automatic restart for the servers.

Use the MNS client in Practice 1 and create a new listener. Then, when the listener receives a Stopped event, the listener executes a `Start` command on the target ECS server.

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

    #Start the ECS instance
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

In your actual scenario, after the `Start` command is executed, you will receive Starting, Running, or Stopped event notifications. In this case, you can proceed with the procedure upon command execution for more detailed O&M with the help of a timer and a counter.

**Practice 3: Automatic removal of preemptible instances from SLB before they are released**

A release alarm event will be sent five minutes before a preemptible instance is released. During these five minutes, you can run some processes without your services being interrupted. For example, you can manually remove the target preemptible instance from the backend SLB server.

Use the MNS client in Practice 1 and create a new listener. Then, when the listener receives the preemptible instance release alarm, the listener calls an SLB SDK.

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

**Note:** 

The event name of the preemptible instance release alarm is Instance:PreemptibleInstanceInterruption", mns\_client.regist\_listener\(ListenerSLB\(Conf.vsever\_group\_id\), 'Instance:PreemptibleInstanceInterruption'\).

In your actual scenario, you need to apply for a new preemptible instance and attach it to SLB to guarantee that your services can run normally.

