AddDnsGtmMonitor (new) {#title}
===============================

Creates a health check task for an address pool of a Global Traffic Manager (GTM) instance.

Debugging 
------------------------------

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Alidns&api=AddDnsGtmMonitor&type=RPC&version=2015-01-09)

Request parameters 
---------------------------------------



|       Parameter        |  Type   | Required |                                   Example                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------|---------|----------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Action                 | String  | Yes      | AddDnsGtmMonitor                                                            | The operation that you want to perform. Set the value to AddDnsGtmMonitor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| AddrPoolId             | String  | Yes      | pool1                                                                       | The ID of the address pool.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| EvaluationCount        | Integer | Yes      | 1                                                                           | The number of consecutive times of failed health check attempts.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Interval               | Integer | Yes      | 60                                                                          | The health check interval. Unit: seconds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| MonitorExtendInfo      | String  | Yes      | {\\"code\\":200,\\"path\\":\\"\\\\index.htm\\",\\"host\\":\\"aliyun.com\\"} | The extended information: * HTTP(S)： * port：检查端口   * host：Host设置   * path：URL路径   * code：返回码大于   * failureRate：失败率   * sni：是否开启sni，仅在HTTPS协议时使用。 * true-开启   * 其他-未开启     * nodeType：地址池类型为DOMAIN时，健康检查监控节点类型： * IPV4   * IPV6       * PING： * failureRate：失败率   * packetNum：ping包数   * packetLossRate：ping丢包率   * nodeType：地址池类型为DOMAIN时，健康检查监控节点类型： * IPV4   * IPV6       * TCP： * port：检查端口   * failureRate：失败率   * nodeType：地址池类型为DOMAIN时，健康检查监控节点类型： * IPV4   * IPV6        |
| ProtocolType           | String  | Yes      | http                                                                        | The health check protocol. Valid values: * HTTP   * HTTPS   * PING   * TCP                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Timeout                | Integer | Yes      | 30000                                                                       | The timeout period. Unit: milliseconds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Lang                   | String  | No       | en                                                                          | The language to return some response parameters. Default value: en. Valid values: en, zh, and ja.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| IspCityNode.N.CityCode | String  | No       | 123                                                                         | The code of the city node to monitor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| IspCityNode.N.IspCode  | String  | No       | 123                                                                         | The code of the Internet provider service (ISP) node to monitor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |



Response parameters 
----------------------------------------



|    Parameter    |  Type  |               Example                |           Description            |
|-----------------|--------|--------------------------------------|----------------------------------|
| MonitorConfigId | String | MonitorConfigId1                     | The ID of the health check task. |
| RequestId       | String | 6856BCF6-11D6-4D7E-AC53-FD579933522B | The ID of the request.           |



Examples 
-----------------------------

Sample requests

    http(s)://alidns.aliyuncs.com/? Action=AddDnsGtmMonitor
    &AddrPoolId=pool1
    &EvaluationCount=1
    &Interval=60
    &MonitorExtendInfo={\"code\":200,\"path\":\"\\index.htm\",\"host\":\"aliyun.com\"}
    &ProtocolType=http
    &Timeout=30000
    &<Common request parameters>

{#request-demo}

Sample success responses

`XML` format

    <RequestId>6856BCF6-11D6-4D7E-AC53-FD579933522B</RequestId>
    <MonitorConfigId>MonitorConfigId1</MonitorConfigId>



`JSON` format

    {
        "RequestId":"6856BCF6-11D6-4D7E-AC53-FD579933522B",
        "MonitorConfigId":"MonitorConfigId1"
        }



Error codes 
--------------------------------

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Alidns).