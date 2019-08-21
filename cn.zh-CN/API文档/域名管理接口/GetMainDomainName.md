# GetMainDomainName {#doc_api_Alidns_GetMainDomainName .reference}

调用GetMainDomainName通过输入的参数，获取主域名名称。

关于主域名和子域名级别，参见[域名级别](https://help.aliyun.com/document_detail/29813.html?spm=a2c4g.11186623.2.16.59502685M6HyqZ)。 如输入`www.abc.com`，则输出abc.com。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=GetMainDomainName&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|GetMainDomainName|系统规定参数。取值：**GetMainDomainName**。

 |
|InputString|String|是|www.example.com|字符串，最长不超过128个字符。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|用户语言。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainLevel|Long|2|输入域名的级别。

 |
|DomainName|String|example.com|域名名称。

 |
|RR|String|www|主机记录信息。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=GetMainDomainName
&InputString=www.example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<GetMainDomainNameResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <DomainName>example.com</DomainName>
      <RR>www</RR>
      <DomainLevel>2</DomainLevel>
</GetMainDomainNameResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RR":"www",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"DomainName":"example.com",
	"DomainLevel":2
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

