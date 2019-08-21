# DescribeDomainRecordInfo {#doc_api_Alidns_DescribeDomainRecordInfo .reference}

调用DescribeDomainRecordInfo获取解析记录的详细信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDomainRecordInfo&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainRecordInfo|系统规定参数。取值：**DescribeDomainRecordInfo**。

 |
|RecordId|String|是|9999985|解析记录的ID 。

 此参数在添加解析时会返回，在获取域名解析列表时会返回。

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
|DomainId|String|00efd71a-770e-4255-b54e-6fe5659baffe|域名ID。

 |
|DomainName|String|中文.com|域名名称。

 |
|GroupId|String|2223|域名分组ID。

 |
|GroupName|String|MyGroup|域名分组名称。

 |
|Line|String|default|解析线路。

 |
|Locked|Boolean|true|解析记录锁定状态，取值：**true/false**。

 |
|Priority|Long|5|MX记录的优先级。

 |
|PunyCode|String|xn--fsq270a.com|只针对中文域名返回punycode码。

 |
|RR|String|@|解析类型。

 |
|RecordId|String|9999985|解析记录的ID。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|Status|String|Enable|解析记录状态，取值：**Enable/Disable**。

 |
|TTL|Long|600|生存时间。

 |
|Type|String|MX|记录类型。

 |
|Value|String|mail.hichina.com|记录值。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeDomainRecordInfo
&RecordId=9999985
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainRecordInfoResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <DomainName>example.com</DomainName>
      <RecordId>9999985</RecordId>
      <RR>@</RR>
      <Type>MX</Type>
      <Value>mail.hichina.com</Value>
      <Line>default</Line>
      <Priority>5</Priority>
      <TTL>600</TTL>
      <Status>Enable</Status>
      <Locked>false</Locked>
</DescribeDomainRecordInfoResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RR":"@",
	"Status":"Enable",
	"Value":"mail.hichina.com",
	"RecordId":"9999985",
	"Type":"MX",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"DomainName":"example.com",
	"Locked":false,
	"Line":"default",
	"TTL":600,
	"Priority":5
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

