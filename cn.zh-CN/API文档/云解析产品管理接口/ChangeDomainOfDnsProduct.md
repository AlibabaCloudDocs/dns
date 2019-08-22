# ChangeDomainOfDnsProduct {#doc_api_Alidns_ChangeDomainOfDnsProduct .reference}

调用ChangeDomainOfDnsProduct更换云解析产品绑定的域名。

**说明：** **无论当前云解析产品是否绑定域名，都调用此接口。从云解析产品中解绑域名，也调用此接口，即NewDomain为空。**

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=ChangeDomainOfDnsProduct&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ChangeDomainOfDnsProduct|系统规定参数。取值：**ChangeDomainOfDnsProduct**。

 |
|InstanceId|String|是|i-7sb|云解析产品ID。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Force|Boolean|否|false|是否强制绑定。

 |
|Lang|String|否|en|语言。

 |
|NewDomain|String|否|newdomain.com|目标绑定域名，如不填写，则为解绑。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|OriginalDomain|String|originaldomain.com|原始绑定的域名，如果为空，则为第一次绑定。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=ChangeDomainOfDnsProduct
&InstanceId=i-7sb
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ChangeDomainOfDnsProductResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <OriginalDomain>originaldomain.com</OriginalDomain>
</ChangeDomainOfDnsProductResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"OriginalDomain":"originaldomain.com",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

