# DescribeDomainInfo {#doc_api_Alidns_DescribeDomainInfo .reference}

调用DescribeDomainInfo根据传入参数查询指定域名的信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDomainInfo&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainInfo|系统规定参数。取值：DescribeDomainInfo。

 |
|DomainName|String|是|example.com|域名名称。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|用户语言。

 |
|NeedDetailAttributes|Boolean|否|false|默认值为**false**，表示不需要细节属性。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AliDomain|Boolean|true|是否为阿里云万网域名。

 |
|AvailableTtls| |\[600,1800,3600,43200,86400\]|可用TTL列表。

 |
|DnsServers| |\["vip3.alidns.com", "vip4.alidns.com"\]|DNS信息。

 |
|DomainId|String|00efd71a-770e-4255-b54e-6fe5659baffe|域名ID。

 |
|DomainName|String|example.com|域名名称。

 |
|GroupId|String|2223|域名分组ID。

 |
|GroupName|String|mygroup|域名分组名称。

 |
|InBlackHole|Boolean|false|是否在黑洞中。

 |
|InClean|Boolean|false|是否在清洗中。

 |
|InstanceId|String|i-7bg|云解析产品ID。

 |
|LineType|String|region\_province|线路类型。

 |
|MinTtl|Long|1|最小TTL。

 |
|PunyCode|String|example.com|只针对中文域名返回punycode码。

 |
|RecordLineTreeJson|String|\{"default":\{\},"unicom":\{\},"telecom":\{\},"mobile":\{\},"edu":\{\},"oversea":\{\},"baidu":\{\},"biying":\{\},"google":\{\}\}|树形化解析线路列表

 |
|RecordLines| | |解析线路数据列表。

 |
|FatherCode|String|internal|父线路Code，如果没有则为空。

 |
|LineCode|String|cn\_region\_xibei|线路Code。

 |
|LineDisplayName|String|中国地区\_西北|线路展示名。

 |
|LineName|String|西北|线路名称。

 |
|RegionLines|Boolean|false|是否是地域线路。

 |
|Remark|String|remark|备注。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|SlaveDns|Boolean|true|是否允许有辅助dns。

 |
|VersionCode|String|version1|云解析版本ID。

 |
|VersionName|String|企业标准版|云解析产品名称。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeDomainInfo
&DomainName=example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainInfoResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <DomainId>00efd71a-770e-4255-b54e-6fe5659baffe</DomainId>
      <DomainName>example.com</DomainName>
      <AliDomain>true</AliDomain>
      <GroupId>2223</GroupId>
      <GroupName>MyGroup</GroupName>
      <InstanceId>i-7bg</InstanceId>
      <VersionCode>version1</VersionCode>
      <PunyCode>example.com</PunyCode>
      <DnsServers>
            <DnsServer>dns1.hichina.com</DnsServer>
            <DnsServer>dns2.hichina.com</DnsServer>
      </DnsServers>
</DescribeDomainInfoResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"GroupName":"MyGroup",
	"PunyCode":"example.com",
	"VersionCode":"version1",
	"InstanceId":"i-7bg",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"AliDomain":"true",
	"DomainName":"example.com",
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

