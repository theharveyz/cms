# View site monitoring data {#concept_id5_zjb_wdb .concept}

This topic describes how to view site monitoring data.

## Overview {#section_cj5_msk_xdb .section}

This page provides data about access to the current site from four dimensions: availability, real-time response time, error distribution, and average response time.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189103684_en-US.png)

The error distribution shows the number of detection results with a status code greater than 399 for each carrier in each region within a specified period of time. You can click on the chart to view error details.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189103688_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189103690_en-US.png)

## China Map {#section_lsk_nhm_xdb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189103697_en-US.png)

If you click a province on the map, the second-level administrative divisions in the provide appear.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113762_en-US.png)

Detailed monitoring data is shown below the map.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113763_en-US.png)

## World Map {#section_wqq_hnq_bhb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/155961891140695_en-US.png)

## Indicator Trends {#section_ckw_y4r_xdb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113764_en-US.png)

## Operator Trends {#section_d4k_npr_xdb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113766_en-US.png)

## Error Rate Trends {#section_ozt_tpr_xdb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113767_en-US.png)

You can click **More** in the **Details** column for a task to view the error details for a specific carrier in a specific city.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113768_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113769_en-US.png)

## Access Strategy {#section_ytz_grr_xdb .section}

This page provides you with detailed detection results for each carrier in each region within a specified period of time.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/15596189113783_en-US.png)

## Procedure {#section_6od_puo_72o .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **New Site Monitor** \> **Site Manage**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6160/155961891140674_en-US.png)

3.  On the Site Monitoring page, click a site name to open the Monitoring overview page. In the left-side navigation pane, click a menu item and then in the main workspace view the corresponding monitoring data.

## Terms {#section_sz4_ysr_xdb .section}

|Term|Description|
|:---|:----------|
|Availability|Number of detection results with a status code less than 400 from all probe points within a specified period of time/Total number of detection results × 100%|
|Total Response Time|The time taken to receive the first byte of an HTTP response after a probe point initiates detection. If the detection request is redirected, the time also includes the time spent to redirect the page.|
|DNS Time|The time for the Domain Name Server \(DNS\) to resolve the domain name. Unit: millisecond.|
|TCPConnect Time|The time taken to write an HTTP request message after a probe point initiates detection. The time does not include the time for the DNS to resolve the domain name.|
|RedirectTime|The time taken to send the first detection request that is not redirected after a probe point initiates detection.|
|Start Transfer Time|The time taken to receive the first byte of an HTTP response after a probe point initiates detection.|
|Pretransfer Time|The time taken to write an HTTP request message after a probe point initiates detection.|
|SSL Connect|The time spent on SSL authentication after a probe point initiates detection.|
|Download Speed|The speed at which probe points read HTTP responses.|
|Download Size|The size of an HTTP response. If the HTTP response contains the `Content-Length` field, the download size equals the value of this field. If the HTTP response does not contain this field, the download size equals the number of bytes that are read from the HTTP response.|

