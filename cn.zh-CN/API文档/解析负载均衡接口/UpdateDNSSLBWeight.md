# UpdateDNSSLBWeight {#doc_api_Alidns_UpdateDNSSLBWeight .reference}

调用UpdateDNSSLBWeight根据传入参数修改解析负载均衡的权重。

 **** 

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=UpdateDNSSLBWeight&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|UpdateDNSSLBWeight|系统规定参数。取值：**UpdateDNSSLBWeight**。

 |
|RecordId|String|是|9999985|解析记录ID。

 |
|Weight|Integer|是|2|要修改的权重值`[1-100]`。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|语言。

 |
|UserClientIp|String|否|1.1.1.1|用户IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RecordId|String|9999985|解析记录ID。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|Weight|Integer|2|修改后的权重值。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=UpdateDNSSLBWeight
&RecordId=9999985
&Weight=2
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateDNSSLBWeightResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <RecordId>9999985</RecordId>
      <Weigth>2</Weigth>
</UpdateDNSSLBWeightResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Weight":2,
	"RecordId":"9999985",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

