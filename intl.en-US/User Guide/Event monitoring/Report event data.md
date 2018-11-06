# Report event data {#concept_ezl_l3b_wdb .concept}

The event monitoring function provides APIs to report events, allowing you to collect and report service exceptions to CloudMonitor. You can configure policies for reported events to receive alerts and notifications.

CloudMonitor supports data reporting using open APIs, Java SDK, and AliCloudCLI.

## Restrictions {#section_mmb_n3j_zdb .section}

-   Single cloud account QPS is limited to 20.
-   Report up to 100 incidents in a single time.
-   Report a maximum of 500kb of data in a single time.

## Report data using open APIs {#section_ktq_43j_zdb .section}

-   Service address:

    ```
    https://metrichub-cms-cn-hangzhou.aliyuncs.com
    ```


-   Request syntax

    ```
    POST /event/custom/upload HTTP/1.1 
    Authorization: <authorizationstring>
    Content-Length:<Content Length>
    Content-MD5:<Content MD5>
    Content-Type:application/json
    Date: <GMT date>
    HOST: maid
    x-cms-signature:hmac-sha1
    x-cms-api-version:1.0
    x-cms-ip:30.27.84.196
    User-Agent:cms-java-sdk-v-1.0
    [{"content":"EventContent","groupId":GroupId,"name":"EventName","time":"20171023T144439.948+0800"}]
    ```


-   Request Parameters

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |name|String|Yes|Event name|
    |groupId|Numerical|Yes.|APP grouping ID to which the event belongs|
    |time|String|Yes.|Event occurrence time|
    |content|String|Yes.|Event details|

    [Request header definition](reseller.en-US/User Guide/Event monitoring/Request header definition.md#)

    [Signature Algorithm](reseller.en-US/User Guide/Event monitoring/Signature Algorithm.md#)


-   Response Element

    The system returns the HTTP status code 200.


-   Example
    -   Request example

        ```
        POST /event/custom/upload HTTP/1.1 
        Host: metrichub-cms-cn-hangzhou.aliyuncs.com
        x-cms-api-version:1.0
        Authorization:YourAccKey:YourAccSecret 
        Host:metrichub-cms-cn-hangzhou.aliyuncs.com"
        Date:Mon, 23 Oct 2017 06:51:11 GMT
        Content-Length:180
        x-cms-signature:hmac-sha1
        Content-MD5:E9EF574D1AEAAA370860FE37856995CD
        x-cms-ip:30.27.84.196
        User-Agent:cms-java-sdk-v-1.0
        Content-Type:application/json
        [{"Content": "123, ABC", "groupid": 100, "name": "event_0", "Time": "loud. 948 + 0800 "}]
        ```

    -   Response example

        ```
        {
           "Code": 200 ",
           "msg": "// return MSG is empty when reporting normally
        }
        ```


## Report data using the Java SDK {#section_zdb_w3j_zdb .section}

-   Maven dependency

    ```
    <dependency>
        <groupId>com.aliyun.openservices</groupId>
        <artifactId>aliyun-cms</artifactId>
        <version>0.1.2</version>
    </dependency>
    ```


-   Sample code

    ```
    public void uploadEvent() throws CMSException, InterruptedException {
            // Initialize Client
            CMSClient cmsClient = new CMSClient(endpoint, accKey, secret);
           // Build 2 incident reports
             CustomEventUploadRequest request = CustomEventUploadRequest.builder()
                        .append(CustomEvent.builder()
                                .setContent("abc,123")
                                .setGroupId(101l)
                                .setName("Event001").build())
                        .append(CustomEvent.builder()
                                .setContent("abc,123")
                                .setGroupId(101l)
                                .setName("Event002").build())
                        .build();
                CustomEventUploadResponse response = cmsClient.putCustomEvent(request);
                List<CustomEvent> eventList = new ArrayList<CustomEvent>();
                eventList.add(CustomEvent.builder()
                        .setContent("abcd,1234")
                        .setGroupId(101l)
                        .setName("Event001").build());
                eventList.add(CustomEvent.builder()
                        .setContent("abcd,1234")
                        .setGroupId(101l)
                        .setName("Event002").build());
                request = CustomEventUploadRequest.builder()
                        .setEventList(eventList).build();
                response = cmsClient.putCustomEvent(request);
        }
    ```


## Ali cloud command line \(CLI\) Way to report data {#section_pvp_1kj_zdb .section}

```
With an Ali cloud account, and generate Sub-Account AK with cloud monitoring privileges (with Sub-Account Security better ).
```

-   Create a sub-account.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/154149089621800_en-US.png)

-   Generate accesskeyid and accesskeysecret for the sub-account.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/154149089621804_en-US.png)

-   Assign CloudMonitor permissions for the sub-account.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/154149089621812_en-US.png)


## Operation procedure {#section_wln_wlj_zdb .section}

1.  Install the tool aliyuncli.

    ```
    System requirements: Linux, UNIX, or Mac OS Environment requirements: Python 2.7.x has been installed.
    ```

    1.  Install Python
        -   If your device is installed with Python 2.7.x, skip this step.
        -   If your device is not installed with Python 2.7.x, run the following command in the command line window to install Python: Make sure that your device is installed with wget.

            ```
            wget https://www.python.org/ftp/python/2.7.8/Python-2.7.8.tgz (or download it in other ways and put it in a certain path)
            tar -zxvf Python-2.7.8.tgz
            cd Python-2.7.8
            ./configure
            make
            sudo make install
            ```

    2.  Install pip
        -   If your device is installed with pip, skip this step.
        -   If your device is not installed with pip, run the following command in the command line window to install pip:

            ```
            curl "https://bootstrap.pypa.io/get-pip.py" -o "pip-install.py"
            sudo python pip-install.py
            ```

        -   The system displays the following similar information, indicating that the installation is successful:

            ```
            Successfully installed pip-7.1.2 setuptools-18.7 wheel-0.26.0
            ```

    3.  Install the command line tool

        If the pip version is too low in the system, it will cause an error in the CLI installation. You can use the following command to upgrade the pip software before performing other operations: Use pip 7.x or later. If your pip is already the latest, skip this step.

        1.  Run the following command in the command line window to upgrade the  pip:

            ```
            sudo pip install -U pip
            ```

            The system displays the following similar information, indicating that the upgrade is successful:

            ```
            Successfully uninstalled pip-7.1.2
            Successfully installed pip-8.1.2
            ```

        2.  Run the following command to install the Alibaba Cloud command line tool:

            ```
            sudo pip install aliyuncli
            ```

            The system displays the following similar information, indicating that the installation is successful:

            ```
            Successfully installed aliyuncli-2.1.2 colorama-0.3.3 jmespath-0.7.1
            ```

    4.  Configure the command-line tool

        ```
        ~ Sudo aliyuncli configure
        Aliyun Access Key ID [*******************a]: youraccesskeyid
        Aliyun Access Key Secret [*******************b]: youraccesskeysecret
        Default Region Id [cn-hangzhou]: cn-hangzhou
        Default output format [json]: json
        ```

2.  Install the CmsSDK
    -   For the Windows operating system, run the following command in the command line window:

        ```
        cd C:\Python27\Scripts
        pip install aliyun-python-sdk-cms
        ```

    -   To update the SDK, run the following command:

        ```
        pip install --upgrade aliyun-python-sdk-cms
        ```

    -   Linux Run the following command in the command line window:

        ```
        sudo pip install aliyun-python-sdk-cms
        ```

    -   To update the SDK, run the following command:

        ```
        sudo pip install —upgrade aliyun-python-sdk-cms
        ```

3.  Report monitoring data

    Use the API PutEvent.

    -   Reporting example for Windows:

        ```
        aliyuncli.exe cms PutEvent --EventInfo "[{'content':'helloworld','time':'20171013T170923.456+0800','name':'ErrorEvent','groupId':'27147'}]"
        ```

    -   Linux Reporting example

        ```
        aliyuncli cms PutEvent --EventInfo "[{'content':'helloworld','time':'20171023T180923.456+0800','name':'ErrorEvent','groupId':'27147'}]"
        ```

    -   If data is reported successfully, the system returns status code 200.

        ```
        {
        "Code":"200"
        }
        ```


## Error codes {#section_ovd_hqj_zdb .section}

|Error code|Meaning|
|:---------|:------|
|200|Normal|
|400|Syntax error in the client request|
|403| Verification failed, speed limit, not authorized|
|500| Internal server error|

## Sub-account authorization description {#section_lvd_lqj_zdb .section}

Subaccount authorization description When the AccessKey of a subaccount is used to report an event, the subaccount must be authorized to manage CloudMonitor. The "cannot upload event" prompt when reporting data if the sub-account is not authorized for cloud monitoring administration, Please use Ram to auth ".

1.  Log on to the [access control Ram console](https://partners-intl.console.aliyun.com/#/ram).
2.  Enter the user management menu.
3.  Click **Authorize** next to the subaccount that is used to report data.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/154149089621813_en-US.png)

4.  On the authorization page, select manage permissions for cloud monitoring, and click OK to save the authorization.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/154149089621815_en-US.png)


