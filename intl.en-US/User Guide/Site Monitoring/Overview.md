# Overview {#concept_eff_yjb_wdb .concept}

This topic provides an overview of site monitoring and relevant application scenarios.

## Scenarios {#section_kj3_y4k_xdb .section}

Site monitoring is a function that simulates user access requests to help you better analyze the behavior of users to your services. This function is available in all Alibaba Cloud regions. The typical application scenarios of site monitoring are as follows.

## Analyze service performance {#section_q3h_jpk_xdb .section}

You can create a site monitoring task to obtain data, such as the time for the Domain Name Server \(DNS\) to resolve a domain name, the time when a connection is established, the time when an endpoint receives the first packet after sending a request, and the time when packets start to download. The data can be helpful for you to discover issues in your services, allowing you to achieve better performance.

## Compare your service performance with that of your peers {#section_bhb_kpk_xdb .section}

You can add the sites you service and those of your peers in the CloudMonitor console as monitoring items, and specify the probe points to detect network quality and service performance at the sites that you service and those of your peers.

## Get probe coverage {#section_z1p_lpk_xdb .section}

Site monitoring is available in all Alibaba Cloud regions. These regions can simulate user behavior and send access requests.

## Detection protocol types {#section_th1_ppk_xdb .section}

|Detection type|Function|
|:-------------|:-------|
|HTTP or HTTPS|Sends an HTTP or HTTPS request to a specific URL or IP address to obtain the availability metrics, response time, and status code. In advanced settings, you can select a request method \(`GET`, `POST`, or `HEAD`\), set cookie and header information, and determine whether the page content matches the specified content.|
|PING|Sends an ICMP request that carries the ping command to a specific URL or IP address. This allows you to obtain the availability metrics, response time, and packet loss rate.|
|TCP|Sends a TCP request to a specific port to obtain the availability metrics, response time, and status code. In advanced settings, you can set the TCP request content and the match response content.|
|UDP|Sends a UDP request to a specific port to obtain the availability metrics, response time, and status code. In advanced settings, you can set the UDP request content and the match response content.|
|DNS|Sends a DNS request to a specific domain to obtain the availability metrics, response time, and status code. In advanced settings, you can specify the type of record that you want to query: **A**, **MX**, **NS**, **CNAME**, **TXT**, or **ANY**.|
|POP3|Sends a POP3 request to a specific URL or IP address to obtain the availability metrics, response time, and status code. In advanced settings, you can set the port, username, password, and whether to establish a secured connection.|
|SMTP|Sends an SMTP request to a specific URL or IP address to obtain the availability metrics, response time, and status code. In advanced settings, you can set the port, username, password, and whether to establish a secured connection.|
|FTP|Sends an FTP request to a specific URL or IP address to obtain the availability metrics, response time, and status code. In advanced settings, you can set the port and whether to establish a secured connection.|

