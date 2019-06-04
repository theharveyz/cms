# Create a site monitoring task {#concept_pv1_btq_ngb .concept}

This topic describes how to create a site monitoring task. It can be used to analyze network quality and service performance.

## Background information {#section_a54_gtq_ngb .section}

Site monitoring is a function that simulates user access requests to help you better analyze the behavior of users to your services. This function is available in all Alibaba Cloud regions. By using site monitoring, you can perform the following actions:

-   Create a site monitoring task to obtain data such as the time for the Domain Name Server \(DNS\) to resolve a domain name, the time when a connection is established, the time when an endpoint receives the first packet after sending a request, and the time when packets start to download. The data can be helpful for you to discover issues in your services, allowing you to achieve better performance.
-   Add the sites you service and those of your peers on the CloudMonitor console as monitoring items, and specify the probe points to detect network quality and service performance at the sites that you service and those of your peers.
-   Simulate user behavior and send access requests from all Alibaba Cloud regions.

## Before you begin {#section_brt_ktq_ngb .section}

-   If you want to set alarm rules when creating a site monitoring task, we recommend that you create contacts and contact groups first. You can select the contact groups when setting alarm rules, and the contact groups will receive notifications when alarms are reported. For information about how to create contacts and contact groups, see [Create an alert contact and an alert contact group](reseller.en-US/User Guide/Alarm service/Alarm contacts/Create an alert contact and an alert contact group.md#).
-   If you want to enable the alarm callback function when setting alarm rules, you need to provide a callback URL that is accessible via the Internet. In addition, enable the URL callback function in your O&M system or message system.

## Procedure {#section_tgx_ktq_ngb .section}

**Note:** When creating a site monitoring task, you can choose to set alarm rules or not as needed.

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **New Site Monitor** \> **Site Manage**.
3.  On the Site Monitoring page, click **New Monitoring Task**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115672/155961879337854_en-US.png)

4.  On the New Task page, set basic information for the site monitoring task.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115672/155961879344577_en-US.png)

    -   **Monitor Type**: Select a monitoring protocol. Valid values: **HTTP\(s\)** | **PING** | **TCP** | **UDP** | **DNS** | **SMTP** | **POP3** | **FTP**.
    -   **Task Name**: the name of the task. The task name contains 4 to 100 characters including letters, numbers, and underscores \(\_\).
    -   **Monitor Address**: the destination address that you want to monitor. Separate multiple addresses into new lines. When you save the task settings, each address is saved as a job.
    -   **Monitoring frequency**: the interval at which the destination address is monitored regularly. Valid values: **1 minute** | **5 minute** | **15 minute** | **30 minute** | **60 minute**. For example, if you set **Monitoring frequency** to **1 minute**, each probe point monitors the destination addresses at 1-minute intervals.
    -   **Advanced Settings**: The advanced settings available vary depending on the protocol specified by the **Monitor Type** parameter. For more information, see [Advanced settings in Monitoring Type](#section_edy_yxs_zgb).
5.  Select or customize probe points.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115672/155961879344578_en-US.png)

    -   **ECS Probe Point**: Select probe points.
    -   **Probe points advanced options**: Customize probe points.
6.  Optional. Set alarm rules.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115672/155961879344579_en-US.png)

    -   **Availability**: Includes four options: **Available probe point ratio**, **Number of probe points available**, **Any status code \(independent alarm\)**, and **All status code \(independent alarm\)**. If the status code for a destination address in the detection results is greater than 399, the destination address is inaccessible. The number of probe points available equals the number of detection results with a status code less than 400 within a monitoring period. The proportion of probe points available is calculated as follows:

        Proportion of probe points available = \(Number of detection results with a status code less than 400 within a monitoring period/Total number of detection results within the same monitoring period\) × 100

    -   **Average response time**: the time taken by all the selected probe points to respond on average within a monitoring period.
    -   **Triggered when threshold is exceeded for**: the number of consecutive times that a metric exceeds its threshold before an alarm is reported. This parameter is used to detect the occasional volatility of the monitoring data.
    -   **Contact Group**: the group of contacts to receive alarm notifications.
    -   **Notification Methods**: the method for receiving alarm notifications.
    -   **Advanced Settings**: Includes three options: **Channel Silence Time**, **Effective time**, and **Alarm Callback**.
        -   **Channel Silence Time**: the interval at which a notification is sent regularly before the reported alarm is cleared.
        -   **Effective time**: the period of time during which the alarm rule is effective. CloudMonitor sends alarm notifications only within the specified period. After the specified period elapses, CloudMonitor records each reported alarm but does not send notifications.
        -   **Alarm Callback**: Enter a URL that is accessible via the Internet. CloudMonitor sends POST requests that carry alarm information to this URL. You must enter a URL based on the HTTP protocol.
7.  Click **Create**.

## Advanced settings in Monitoring Type {#section_edy_yxs_zgb .section}

-   **Advanced settings for HTTP\(s\)** 

    |Parameter|Value|Required|Description|
    |---------|-----|--------|-----------|
    |Monitor Address|URL|Yes| We recommend that you include a schema into every entered address, for example, **https://www.alibabacloud.com**.

 If you enter an address that does not contain a schema, CloudMonitor adds **http** as a schema to this address.

 |
    |Request content| Form data or JSON object

 |No|If the request content is in the JSON format, ensure that the entered JSON objects are included in braces \(\{\}. If you do not include JSON objects into braces \(\{\}\), CloudMonitor regards them to be form data.|
    |Request method|A selected option|Yes| Valid values: **GET** | **POST** | **HEAD**.

 Default value: **GET**.

 |
    |Match response method|A selected option|Yes| When the match response content is specified, CloudMonitor reads the first 64 KB in the body of the response message that is sent from the HTTP server to search for the specified content. The result is one of the following:

     1.  The response contains the specified content.
    2.  The response does not contain the specified content.
 CloudMonitor determines whether to trigger an alarm based on the specified match response method.

 Alibaba Cloud probe points support match response content in English.

 |
    |Match response content|Text|No|
    |HTTP request header|Lines of text|No| The format of HTTP request header information is as follows: `key1:value1 carriage return linefeed key2:value2`. CloudMonitor presets the following item in the request header:

 Host: $ \{Domain name specified in Monitor Address\}

 Pragma: no-cache

 Cache-Control: no-cache

 User-Agent: Chrome/57

 Accept: \*/\*

 If the request content is a form, the request header may contain the following item:

 Content-Type: application/x-www-form-urlencoded;charset=UTF-8

 If your HTTP request header contains one or more of the preceding items, these items are overwritten by your settings.

 According to the HTTP protocol, CloudMonitor converts the keys in the request header into an MIME header in the canonical format:

     1.  The first letter and the letter that follows a hyphen \(-\) in a key are capitalized. For example, `accept-encoding` is converted into `Accept-Encoding`.
    2.  If a key contains spaces or other invalid characters, it remains unchanged.
 |
    |Cookie|N/A|No|Enter cookie text based on the HTTP protocol.|
    |HTTP Authentication Username|Username|No|This authentication refers to the basic authentication by the HTTP protocol.|
    |HTTP Authentication Password|Password|No|

-   **Advanced settings for PING** 

    |Parameter|Value|Required|
    |---------|-----|--------|
    |Monitor Address|Domain name or IP address|Yes|
    |Number of ping packets|Positive integer|Yes|

    **Note:** The **Number of ping packets** parameter indicates the number of times that the ping command is initiated. Value range: 1 to 40. Default value: 20.

-   **Advanced settings for TCP and UDP** 

    |Parameter|Value|Required|Description|
    |---------|-----|--------|-----------|
    |Monitor Address|Domain name or IP address|Yes|None|
    |Request content format|A selected option|Yes|Valid when the request content is specified. Valid values: **Hexadecimal Format** | **Text**.|
    |Request content| Text or hexadecimal text

 |No| Text: a string of visible text characters. The text format does not support escape characters. That is, `\n` is not converted into a new line entered, but rather the system regards it as two characters: a backward slash \(\\\) and a letter *n*.

 Hexadecimal Format: When the request content is a byte string that cannot be represented by a text string, you can convert the byte string into a hexadecimal string. The conversion rules are as follows: Each byte is converted into a 2-byte hexadecimal string. For example, \(byte\)1 is converted into a hexadecimal string 01, and \(byte\)27 is converted into a hexadecimal string 1B.

 According to the conversion rules, the binary array "\{\(byte\)1, \(byte\)27\}" in Java format is converted into the following hexadecimal string: 011b or 011B. CloudMonitor does not distinguish between uppercase and lowercase letters for hexadecimal strings. Enter the string 011B in the **Request content** field and set **Request content format** to **Hexadecimal Format**.

 |
    |match response content format|A selected option|Yes|Valid when the match response content is specified. Valid values: **Hexadecimal Format** | **Text**.|
    |Match response content| Text or hexadecimal text

 |No|For more information, see the **Request content** parameter.|

-   **Advanced settings for DNS** 

    |Parameter|Value|Required|Description|
    |---------|-----|--------|-----------|
    |Monitor Domain Name|Domain name|Yes| |
    |DNS query type|A selected option|Yes| Valid values: **A** | **MX** | **NS** | **CNAME** | **TXT** | **ANY**.

 Default value: **A**.

 |
    |DNS server|DNS IP address|No|If this parameter is unspecified, CloudMonitor uses the default DNS IP address. You can enter a domain name or an IP address.|
    |Expected to resolve IP|Lines of text|No| Enter a list of domain names or IP addresses that you want to resolve. Each line represents a domain name or an IP address.

 The detection is successful only when the specified list is a subset of the DNS list.

 |

-   **Advanced settings for POP3** 

    |Parameter|Value|Required|Description|
    |---------|-----|--------|-----------|
    |Monitor Address|URL|Yes| If you select the POP3\(s\) protocol, every address that you enter must contain a schema, for example, **pop3s://pop3.aliyun.com**.

 If you enter an address that does not contain a schema, CloudMonitor adds **pop3** as a schema to this address.

 POP3\(s\) encrypts data by using TLS.

 |
    |username|Text|Yes| Your account is authenticated by using the USER and PASS commands.

 Make sure that you enter a valid username and password. CloudMonitor detects the Internet at the intervals specified by the **Monitoring frequency** parameter. If the username and password are invalid, frequent detection to a party may cause this party to block your account.

 |
    |Password|Text|Yes|

-   **Advanced settings for SMTP** 

    |Parameter|Value|Required|Description|
    |---------|-----|--------|-----------|
    |Monitor Address|URL|Yes| Every address that you enter must contain a schema, for example, **smtp://smtp.aliyun.com**.

 If you enter an address that does not contain a schema, CloudMonitor adds **smtp** as a schema to this address.

 SMTP uses the STARTTLS command to negotiate with the server on encryption. When a secured connection is used, the authentication information is also encrypted.

 |
    |username|Text|Yes| Your account is authenticated by using the PLAIN command.

 Make sure that you enter a valid username and password. CloudMonitor detects the Internet at the intervals specified by the **Monitoring frequency** parameter. If the username and password are invalid, frequent detection to a party may cause this party to block your account.

 |
    |Password|Text|Yes|

-   **Advanced settings for FTP** 

    |Parameter|Value|Required|Description|
    |---------|-----|--------|-----------|
    |Monitor Address|URL|Yes|Example: **ftp://smtp.aliyun.com**.|
    |Are you anonymous login|A selected option|Yes| Valid values: **Anonymous Logon** | **Authentication Required**. Default value: **Anonymous Logon**.

 If you select **Authentication Required**, you must enter a valid username and password.

 |
    |username|Text| | The username and password used for FTP authentication.

 If you select **Anonymous Logon**, the username and password are anonymous and ftp@example.com, respectively.

 |
    |Password|Text| |


