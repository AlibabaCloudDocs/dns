# AddDomain {#doc_api_Alidns_AddDomain .reference}

调用AddDomain根据传入参数添加域名。

**说明：** 域名合法性判断参见[域名合法性](https://help.aliyun.com/document_detail/29810.html?spm=a2c4g.11186623.2.16.168c6938fXKYGp)。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=AddDomain&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AddDomain|系统规定参数。取值：**AddDomain**。

 |
|DomainName|String|是|中文.com|域名名称。

 |
|AccessKeyId|String|否|your\_accessskey\_id|您的AccessKey ID。

 |
|GroupId|String|否|2223|域名分组ID。默认为默认分组的GroupId。

 |
|Lang|String|否|en|语言。

 |
|ResourceGroupId|String|否|rg-resourcegroupid|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DnsServers| |\{"DnsServer": \["ns1.alidns.com","ns2.alidns.com"\]\}|域名在解析系统中的DNS列表。

 |
|DomainId|String|00efd71a-770e-4255-b54e-6fe5659baffe|域名ID。

 |
|DomainName|String|中文.com|域名名称。

 |
|GroupId|String|2223|域名分组ID。

 |
|GroupName|String|MyGroup|域名分组名称。

 |
|PunyCode|String|xn--fsq270a.com|只针对中文域名返回punycode码。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AddDomain
&DomainName=中文.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AddDomainResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <DomainId>00efd71a-770e-4255-b54e-6fe5659baffe</DomainId>
      <DomainName>中文.com</DomainName>
      <GroupId>2223</GroupId>
      <GroupName>MyGroup</GroupName>
      <PunyCode>xn--fsq270a.com</PunyCode>
      <DnsServers>
            <DnsServer>dns1.hichina.com</DnsServer>
            <DnsServer>dns2.hichina.com</DnsServer>
      </DnsServers>
</AddDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"GroupName":"MyGroup",
	"PunyCode":"xn--fsq270a.com",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"DomainName":"中文.com",
	"DomainId":"00efd71a-770e-4255-b54e-6fe5659baffe",
	"DnsServers":{
		"DnsServer":[
			"ns1.alidns.com",
			"ns2.alidns.com"
		]
	},
	"GroupId":"2223"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

