# ModifyHichinaDomainDNS {#doc_api_Alidns_ModifyHichinaDomainDNS .reference}

调用ModifyHichinaDomainDNS根据传入参数修改域名DNS服务器名称。

修改成功后，DNS会被修改为云解析DNS（hichina.com结尾的DNS）。

**说明：** **使用前提：适用于阿里云注册域名，且当前DNS服务器是第三方DNS的域名使用。**

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=ModifyHichinaDomainDNS&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyHichinaDomainDNS|系统规定参数。取值：**ModifyHichinaDomainDNS**。

 |
|DomainName|String|是|example.com|域名名称。

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
|NewDnsServers| |\{"DnsServer": \["dns9.hichina.com","dns10.hichina.com"\]\}|域名修改后的DNS列表。

 |
|OriginalDnsServers| |\{"DnsServer": \["NS3.DNSV5.COM","NS4.DNSV5.COM"\]\}|域名修改前的DNS列表。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyHichinaDomainDNS
&DomainName=example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyHichinaDomainDNSResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <OriginalDnsServers>
            <DnsServer>NS3.DNSV5.COM</DnsServer>
            <DnsServer>NS4.DNSV5.COM</DnsServer>
      </OriginalDnsServers>
      <NewDnsServers>
            <DnsServer>dns9.hichina.com</DnsServer>
            <DnsServer>dns10.hichina.com</DnsServer>
      </NewDnsServers>
</ModifyHichinaDomainDNSResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"OriginalDnsServers":{
		"DnsServer":[
			"NS3.DNSV5.COM",
			"NS4.DNSV5.COM"
		]
	},
	"NewDnsServers":{
		"DnsServer":[
			"dns9.hichina.com",
			"dns10.hichina.com"
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

