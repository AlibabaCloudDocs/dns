DescribeDnsGtmMonitorConfig (new) {#title}
==========================================

Queries the health check configurations of an address pool of a Global Traffic Manager (GTM) instance.

Debugging 
------------------------------

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Alidns&api=DescribeDnsGtmMonitorConfig&type=RPC&version=2015-01-09)

Request parameters 
---------------------------------------



|    Parameter    |  Type  | Required |           Example           |                                            Description                                            |
|-----------------|--------|----------|-----------------------------|---------------------------------------------------------------------------------------------------|
| Action          | String | Yes      | DescribeDnsGtmMonitorConfig | The operation that you want to perform. Set the value to DescribeDnsGtmMonitorConfig.             |
| MonitorConfigId | String | Yes      | MonitorConfigId1            | The ID of the health check task.                                                                  |
| Lang            | String | No       | en                          | The language to return some response parameters. Default value: en. Valid values: en, zh, and ja. |



Response parameters 
----------------------------------------



|     Parameter     |         Type         |                                   Example                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------|----------------------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CreateTime        | String               | 2017-12-28T13:08Z                                                           | The time when the health check task was created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| CreateTimestamp   | Long                 | 1527690629357                                                               | The timestamp that indicates when the health check task was created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| EvaluationCount   | Integer              | 1                                                                           | The number of consecutive times of failed health check attempts.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Interval          | Integer              | 1                                                                           | The health check interval. Unit: seconds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| IspCityNodes      | Array of IspCityNode |                                                                             | The monitored node.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| IspCityNode       |                      |                                                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| CityCode          | String               | 572                                                                         | The code of the monitored city node.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| CityName          | String               | Qingdao                                                                     | The display name of the monitored city node.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| CountryCode       | String               | 001                                                                         | The code of the country/region.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| CountryName       | String               | China                                                                       | The display name of the country/region.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| IspCode           | String               | 123                                                                         | The code of the monitored Internet service provider (ISP) node.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| IspName           | String               | Alibaba Cloud                                                               | The name of the monitored ISP node.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| MonitorConfigId   | String               | MonitorConfigId1                                                            | The ID of the health check task.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| MonitorExtendInfo | String               | {\\"code\\":200,\\"path\\":\\"\\\\index.htm\\",\\"host\\":\\"aliyun.com\\"} | The extended information: * HTTP(S)： * port：检查端口   * host：Host设置   * path：URL路径   * code：返回码大于   * failureRate：失败率   * sni：是否开启sni，仅在HTTPS协议时使用。 * true-开启   * 其他-未开启     * nodeType：地址池类型为DOMAIN时，健康检查监控节点类型： * IPV4   * IPV6       * PING： * failureRate：失败率   * packetNum：ping包数   * packetLossRate：ping丢包率   * nodeType：地址池类型为DOMAIN时，健康检查监控节点类型： * IPV4   * IPV6       * TCP： * port：检查端口   * failureRate：失败率   * nodeType：地址池类型为DOMAIN时，健康检查监控节点类型： * IPV4   * IPV6        |
| ProtocolType      | String               | http                                                                        | The health check protocol. Valid values: * HTTP   * HTTPS   * PING   * TCP                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| RequestId         | String               | 6856BCF6-11D6-4D7E-AC53-FD579933522B                                        | The ID of the request.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Timeout           | Integer              | 3000                                                                        | The timeout period. Unit: milliseconds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| UpdateTime        | String               | 2018-01-03T08:57Z                                                           | The time when the health check task was updated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| UpdateTimestamp   | Long                 | 1527690629357                                                               | The time when the health check task was updated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |



Examples 
-----------------------------

Sample requests

    http(s)://alidns.aliyuncs.com/? Action=DescribeDnsGtmMonitorConfig
    &MonitorConfigId=MonitorConfigId1
    &<Common request parameters>

{#request-demo}

Sample success responses

`XML` format

    <RequestId>6856BCF6-11D6-4D7E-AC53-FD579933522B</RequestId>
    <Timeout>3000</Timeout>
    <ProtocolType>http</ProtocolType>
    <IspCityNodes>
        <IspCityNode>
            <CityCode>572</CityCode>
            <IspName>Alibaba Cloud</IspName>
            <CountryName>China</CountryName>
            <CityName>Qingdao</CityName>
            <CountryCode>001</CountryCode>
            <IspCode>123</IspCode>
        </IspCityNode>
    </IspCityNodes>
    <CreateTime>2017-12-28T13:08Z</CreateTime>
    <UpdateTime>2018-01-03T08:57Z</UpdateTime>
    <EvaluationCount>1</EvaluationCount>
    <MonitorExtendInfo>"{\"code\":200,\"path\":\"\\index.htm\",\"host\":\"aliyun.com\"}"</MonitorExtendInfo>
    <UpdateTimestamp>1527690629357</UpdateTimestamp>
    <MonitorConfigId>MonitorConfigId1</MonitorConfigId>
    <CreateTimestamp>1527690629357</CreateTimestamp>
    <Interval>1</Interval>



`JSON` format

    {
            "RequestId": "6856BCF6-11D6-4D7E-AC53-FD579933522B",
            "Timeout": "3000",
            "ProtocolType": "http",
            "IspCityNodes": {
                    "IspCityNode": [{
                            "CityCode": "572",
                            "IspName":"Alibaba Cloud",
                            "CountryName":"China",
                            "CityName":"Qingdao",
                            "CountryCode": "001",
                            "IspCode": "123"
                    }]
            },
            "CreateTime": "2017-12-28T13:08Z",
            "UpdateTime": "2018-01-03T08:57Z",
            "EvaluationCount": "1",
            "MonitorExtendInfo": "\"{\\\"code\\\":200,\\\"path\\\":\\\"\\\\index.htm\\\",\\\"host\\\":\\\"aliyun.com\\\"}\"",
            "UpdateTimestamp": "1527690629357",
            "MonitorConfigId": "MonitorConfigId1",
            "CreateTimestamp": "1527690629357",
            "Interval": "1"
    }



Error codes 
--------------------------------

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Alidns).