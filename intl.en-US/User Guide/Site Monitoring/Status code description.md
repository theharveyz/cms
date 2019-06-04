# Status code description {#concept_nvf_32b_h2b .concept}

Each site monitoring protocol returns a status code during the detection process. Common status codes are described as follows.

## Definitions of custom status codes of CloudMonitor {#section_py1_q2b_h2b .section}

|Protocols| Status code|Description |
|:--------|:-----------|:-----------|
|HTTP|610|Timeout \(connection timeout, SSL Certificate exchange timeout, 30 s\)|
|HTTP|613|DNS resolution Error|
|HTTP|615|The content does not match|
|HTTP|616|An error occurred while performing the authentication.|
|HTTP|611|Detection failure due to other reasons|
|HTTP|617| Maximum jump count exceeded

 The Max number of 3xx Redirects allowed at the ECS probe point is 5 times

 The maximum number of 3xx redirected jumps allowed by the carrier probe point is 2

 |
|HTTP|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|
|Ping|550|Network is not available|
|Ping|610|All sent packets receive no response in 2 seconds despite stable network condition.|
|Ping|613||Failed IP address resolution based on the host file||
|Ping|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|
|TCP|550||Failed to enable the socket. A typical cause is that the system sources have run out.||
|TCP|610||Failed response reception \(time-out or no response\)||
|TCP|611|Failed connection \(time-out or rejected by the peer end\)||
|TCP|615|The content does not match|
|TCP|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|
|UDP|550||Failed to enable the socket. A typical cause is that the system sources have run out.||
|UDP|611|Failed connection \(failed resolution based on the host file\)||
|UDP|610||Failed sending or reception||
|UDP|615|The content does not match|
|UDP|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|
|DNS|610|DNS resolution failed|
|DNS|613||DNS query communication error||
|DNS|615|The content does not match|
|DNS|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|
|SMTP|610|Connection time-out|
|SMTP|611|Your site could not be accessed successfully, failure Reasons include, but are not limited to, DNS resolution failure, Incorrect email format, failed to initialize SMTP client, and so on|
|SMTP|616|Login denied|
|SMTP|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|
|POP3|611|Unable to successfully access your site|
|POP3|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|
|FTP|610|FTP Transfer failed|
|FTP|611|Failure caused by other factors, such as failure of DNS resolution, failure of TCP connection, etc.|
|FTP|616|A RAM user fails to log on to the console|
|FTP|703|The internal network detection of the server is prohibited. The internal network probe can use the [availability monitoring function](reseller.en-US/User Guide/Availability monitoring/Manage availability monitoring.md#).|

## Definitions of standard HTTP status codes {#section_czb_bfb_h2b .section}

|Status code|Description|Note|
|:----------|:----------|:---|
|200|Request completed|Status Codes 2XX indicate that the service is normal.|
|300|Multiple choices|The server can perform multiple operations based on the request. The server selects one operation to perform based on the user agent, or provides a list of operations for the user agent to choose.|
|301|Moved permanently|The requested webpage has been permanently moved to a new location. When the server returns Status Code 301 \(in response to a GET or HEAD request\), it automatically redirects the user agent to the new location. You must use this status code to notify Googlebot that a webpage or website has been permanently transferred to a new location.|
|302|Moved temporarily|The server returns the response from a webpage in a different location, but the user agent must use the original location for subsequent requests. Similar to Code 301 in response to a GET or HEAD request, this code means that the server automatically redirects the user agent to a different location.|
|303|See other|The server returns this code when the user agent must send GET requests separately for different locations for response retrieval. For all requests except HEAD requests, the server automatically jumps to other locations.|
|304|Not modified|The requested webpage has not been modified since the last request. The webpage content is not returned when the server returns Status Code 304.|
|305|Use proxy|The user agent can access the requested webpage only by proxy. If the server returns this code, it also specifies the proxy that the user agent must use.|
|400|Bad request|The server does not understand the syntax of the request.|
|401|Unauthorized|Authentication is required for the request. The server may return Status Code 401 in response to the webpage access request after logon.|
|403|Forbidden|The server rejects the request.|
|404|Not found|The server cannot find the requested webpage. For example, if the requested webpage does not exist on the server, the server returns Status Code 404.|
|405|Method not allowed|The method specified in the request is forbidden.|
|406|Not acceptable|The content characteristics of the request cannot be used to respond to the webpage access request.|
|407|Proxy authentication required|This status code is similar to 401 \(unauthorized\), but it specifies that the user agent must use a proxy for authentication. If the server returns this code, it also specifies the proxy that the user agent must use.|
|408|The request times out.|The server timed out waiting for the request.|
|409|Conflict|A conflict occurred when the server completed the request. The server must include the conflict information in the response packet. The server may return Status Code 409 and provide a list of differences between two conflicting requests when responding to the PUT request that conflicts with the previous request.|
|411|Length required|The server does not accept the request that contains header fields of invalid content length.|
|412|Precondition failed|The server does not meet one of the preconditions that the user agent sets in the request.|
|413|Request entity too large|The server cannot process the request because the request entity is too large and exceeds the server's processing capability.|
|414|Requested URI too long|The server cannot process the request because the requested URI \(usually the URL of the target website\) is too long.|
|415|Unsupported media type|The request format is not supported by the requested webpage.|
|416|Range not satisfiable|The server returns this code if the request is out of the valid range of the requested webpage.|
|417|Expectation failed|The server does not meet the requirements of the \*\*Expect\*\* request-header field.|
|499|Client closed request|This status code is returned when the client closes the connection because it takes a long time for the server to process the request.|
|500|Internal server error|The request cannot be completed due to a server error.|
|501|Not implemented|This code is returned when the server does not have the function to complete the request. For example, when the server cannot identify the request method, it may return this status code.|
|502|Bad gateway|The gateway or proxy server receives an invalid response from the upstream server.|
|503|Service unavailable|The server is currently unavailable \(due to overload or shutdown for maintenance\). The unavailable state is temporary.|
|504|Gateway time-out|The gateway or proxy server failed to receive requests from the upstream server in time.|
|505|HTTP version not supported|The server does not support the HTTP version in the request.|

