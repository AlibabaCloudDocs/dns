# DeleteDomain {#doc_api_Alidns_DeleteDomain .reference}

调用DeleteDomain根据传入参数删除域名。

-   由于万网域名的特殊性，因此在DNS API中禁止删除万网域名。
-   不存在的域名情况包括，此域名是未注册的域名、该域名在本账户下不存在或者请求参数中的域名格式错误等。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DeleteDomain&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteDomain|系统规定参数。取值：**DeleteDomain**。

 |
|DomainName|String|是|example.com|域名名称。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|用户语言。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|example.com|域名名称。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteDomain
&DomainName=example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteDomainResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <DomainName>example.com</DomainName>
</DeleteDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"DomainName":"example.com"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

