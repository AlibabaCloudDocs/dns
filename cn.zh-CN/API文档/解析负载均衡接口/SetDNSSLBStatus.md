# SetDNSSLBStatus {#doc_api_Alidns_SetDNSSLBStatus .reference}

调用SetDNSSLBStatus根据传入参数开关解析负载均衡。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=SetDNSSLBStatus&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetDNSSLBStatus|系统规定参数。取值：SetDNSSLBStatus。

 |
|SubDomain|String|是|www.abc.com|需要负载均衡的子域名，其中aliyun.com为错误参数，请使用@.aliyun.com。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|DomainName|String|否|abc.com|域名名称。

 |
|Lang|String|否|en|语言。

 |
|Open|Boolean|否|true|是否开启解析负载均衡。取值：

 -   **true**（默认）：开启
-   **false**：关闭

 |
|UserClientIp|String|否|1.1.1.1|用户IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Open|Boolean|true|解析负载均衡的最新状态。

 |
|RecordCount|Long|8|符合规则的A记录数量。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=SetDNSSLBStatus
&SubDomain=www.abc.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetDNSSLBStatusRecordsResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <RecordCount>8</RecordCount>
      <Open>true</Open>
</SetDNSSLBStatusRecordsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Open":true,
	"RecordCount":8,
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

