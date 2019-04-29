# Report custom event data {#concept_ezl_l3b_wdb .concept}

Event monitoring provides APIs for reporting custom events. You can use the APIs to collect event-related exceptions and report them to CloudMonitor. You can also configure alert rules to receive alert notification when an event-related exception occurs.

CloudMonitor provides three methods to report data: APIs, Java SDK, and Alibaba Cloud CLI.

## Limits {#section_mmb_n3j_zdb .section}

-   Each Alibaba Cloud account can send up to 20 report requests per second.
-   Each report can contain up to 100 events.
-   Each report can contain up to 500 KB of data.

## Report data through APIs {#section_ktq_43j_zdb .section}

-   **Endpoints**

    `https://metrichub-cms-cn-hangzhou.aliyuncs.com`


-   **Request syntax**

    ```
    POST /event/custom/upload HTTP/1.1 
    Authorization:<AuthorizationString>
    Content-Length:<Content Length>
    Content-MD5:<Content MD5>
    Content-Type application/json
    Date:<GMT Date>
    Host: metrichub-cms-cn-hangzhou.aliyuncs.com
    x-cms-signature:hmac-sha1
    x-cms-api-version:1.0
    x-cms-ip:30.27.84.196
    User-Agent:cms-java-sdk-v-1.0
    [{"content":"EventContent","groupId":GroupId,"name":"EventName","time":"20171023T144439.948+0800"}]
    ```


-   **Request parameters**

    |Name|Type|Required?|Description|
    |:---|:---|:--------|:----------|
    |name|String|Yes|The name of the event|
    |groupId|Numerical|Yes|The ID of the application group, to which the event belongs|
    |time|String|Yes|The time when the event occurs|
    |content|String|Yes|The event details|


-   **Request header definition**

    The following table lists the request headers of event monitoring APIs.

    |Header|Type|Description|
    |:-----|:---|:----------|
    |Authorization|String|The authorization string. Content: AccessKeyId:SignString|
    |User-Agent|String|The client description.|
    |Content-MD5|String|The uppercase string obtained after performing MD5 computation on the value of the Body field in the request. If the request does not have the Body field, this request header is not required.|
    |Content-Length|Numerical|The Body field length in the HTTP request as defined in RFC 2616. If the request does not have the Body field, this request header is not required.|
    |Content-Type|String|The Body field type in the HTTP request. Valid values: application and json.|
    |Date|String|The standard timestamp header of the HTTP request. This header follows the RFC 1123 format and uses GMT standard time, such as Mon, 3 Jan 2010 08:33:47 GMT.|
    |Host|String|The full host name of the HTTP request. This header does not include the protocol header such as https://. For example, metrichub-cms-cn-hangzhou.aliyuncs.com.|
    |x-cms-api-version|String|The API version. The current version is 1.0.|
    |x-cms-signature|String|The signature algorithm. Currently, the only supported signature algorithm is HMAC-SHA1.|
    |x-cms-ip|String|The IP address of the machine that reports the event, such as 10.1.1.1.|


-   **Signature algorithm**

    Currently, the only supported signature algorithm is HMAC-SHA1.

    1.  Prepare an Alibaba Cloud AccessKey pair.

        To generate a digital signature for an API request, you must use an AccessKey pair that is composed of an AccessKey ID and an AccessKey Secret. You can use an existing AccessKey pair or create a new one. The AccessKey pair must be in the **Active** state.

    2.  Generate a signature string for the request

        An API signature string consists of the Method, Header, and Body fields of the HTTP request.

        ```
        SignString = VERB + "\n"
                     + CONTENT-MD5 + "\n"
                     + CONTENT-TYPE + "\n"
                     + DATE + "\n"
                     + CanonicalizedHeaders + "\n"
                     + CanonicalizedResource
        ```

        In the preceding formula, `\n` indicates the newline escape character and the plus sign \(`+`\) indicates the string concatenation operator. The other parts are defined as follows:

        |Name|Definition|Examples|
        |:---|:---------|:-------|
        |VERB|The method name of the HTTP request|PUT, GET, and POST|
        |CONTENT-MD5|The MD5 value of the Body field in the HTTP request, which must be an uppercase string|875264590688CA6171F6228AF5BBB3D2|
        |CONTENT-TYPE|The Body field type in the request|application/json|
        |DATE|The standard timestamp header of the HTTP request, which follows the RFC 1123 format and uses GMT standard time|Mon, 3 Jan 2010 08:33:47 GMT|
        |CanonicalizedHeaders|The string constructed by the custom headers prefixed with x-cms and x-acs in the HTTP request|x-cms-api-version:0.1.0\\nx-cms-signature|
        |CanonicalizedResource|The string constructed by the HTTP request resources, as described in the following section|/event/custom/upload|

        CanonicalizedHeaders in the preceding table is constructed as follows:

        1.  Convert the names of all HTTP request headers prefixed with `x-cms` and `x-acs` to lowercase letters.
        2.  Sort the CMS custom request headers obtained in the preceding step in ascending lexicographical order.
        3.  Delete any space on either side of a delimiter between the request header and content.
        4.  Separate all headers and content with separators \(`\n`\) to form the final CanonicalizedHeaders.
        CanonicalizedResource in the preceding table is constructed as follows:

        1.  Set CanonicalizedResource as an empty string \(""\).
        2.  Place the URI that you want to access, such as `/event/custom/upload`, between the quotation marks.
        3.  If the request contains a query string \(`QUERY_STRING`\), add a question mark \(`?`\) and the query string to the end of the CanonicalizedResource string.

            `QUERY_STRING` is the lexicographic string of the request parameters included in the URL. Equal signs \(`=`\) are used between the names and values of parameters to form a string. The parameter name-value pairs are then sorted in ascending lexicographical order and connected with ampersands \(`&`\) to form a string. The formula is as follows:

            ```
            QUERY_STRING = "KEY1=VALUE1" + "&" + "KEY2=VALUE2" 
            ```

    3.  Generate a digital signature for the request

        Currently, the only supported signature algorithm is HMAC-SHA1. The following formula is used to generate a signature:

        ```
        Signature = base16(hmac-sha1(UTF8-Encoding-Of(SignString), AccessKeySecret))
        ```


-   **Response elements**

    The system returns the HTTP status code 200.


-   **Examples**
    -   Sample request

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
        [{"content":"123,abc","groupId":100,"name":"Event_0","time":"20171023T144439.948+0800"}]
        ```

    -   Sample response

        ```
        {
          "code":"200",
          "msg":""//The returned msg is null when the reporting is normal.
        }
        ```


## Report data through Java SDK {#section_zdb_w3j_zdb .section}

-   **Maven dependency**

    ```
    <dependency> 
        <groupId>com.aliyun.openservices</groupId> 
        <artifactId>aliyun-cms</artifactId>
        <version>0.1.2</version>
    </dependency> 
    ```


-   **Sample code**

    ```
    public void uploadEvent() throws CMSException, InterruptedException {
            // Initialize the client.
            CMSClient cmsClient = new CMSClient(endpoint, accKey, secret);
           //Construct two events to be reported.
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


## Report data through Alibaba Cloud CLI {#section_pvp_1kj_zdb .section}

1.  **Prerequisites** 

    Ensure that you have created an Alibaba Cloud account, created a RAM user for your account, and generated a RAM user AK with CloudMonitor permissions.

    1.  Create a RAM user.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/15565291354830_en-US.png)

    2.  Generate an AccessKey ID and an AccessKey Secret for the RAM user.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/15565291354831_en-US.png)

    3.  Grant CloudMonitor permissions to the RAM user.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/15565291384832_en-US.png)

2.  **Install CMS SDK**
    -   The installation method for a Windows system is as follows:

        ```
        cd C:\Python27\Scripts
        pip install aliyun-python-sdk-cms
        ```

        Run the following command to update the SDK:

        ```
        pip install --upgrade aliyun-python-sdk-cms
        ```

    -   The installation method for a Linux system is as follows:

        ```
        sudo pip install aliyun-python-sdk-cms
        ```

        Run the following command to update the SDK:

        ```
        sudo pip install —upgrade aliyun-python-sdk-cms
        ```

3.  **Report monitoring data**

    Use the PutEvent API to report the monitoring data.

    -   Example for a Windows system:

        ```
        aliyuncli.exe cms PutEvent --EventInfo "[{'content':'helloworld','time':'20171013T170923.456+0800','name':'ErrorEvent','groupId':'27147'}]"
        ```

    -   Example for a Linux system:

        ```
        aliyuncli cms PutEvent --EventInfo "[{'content':'helloworld','time':'20171023T180923.456+0800','name':'ErrorEvent','groupId':'27147'}]"
        ```

    -   If the data is reported successfully, status code 200 is returned.

        ```
        {
        "Code":"200"
        }
        ```


 **Error codes**

|Error code|Description|
|:---------|:----------|
|200|Normal|
|400|Syntax error in the client request|
|403|Verification failure, speed limit, or not authorized|
|500|Internal server error|

**RAM user authorization**

You must grant CloudMonitor permissions to the corresponding RAM user before event data can be reported with the RAM user AK. If you do not grant the permissions, when you report data, the prompt "cannot upload event, please use ram to auth" is displayed.

1.  Log on to the [RAM console](https://ram.console.aliyun.com/#/overview).
2.  In the left-side navigation pane, click **Users**.
3.  On the Users page that appears, click **Authorize** in the Actions column corresponding to the RAM user.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/15565291414851_en-US.png)

4.  On the authorization page, select **AliyunCloudMonitorFullAccess** and click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6163/15565291414852_en-US.png)


