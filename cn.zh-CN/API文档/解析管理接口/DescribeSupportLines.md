# DescribeSupportLines {#doc_api_Alidns_DescribeSupportLines .reference}

调用DescribeSupportLines查询云解析支持的所有线路列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeSupportLines&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSupportLines|系统规定参数。取值：**DescribeSupportLines**。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|DomainName|String|否|example.com|域名名称。

 |
|Lang|String|否|en|语言。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RecordLines| | |云解析线路列表。

 |
|FatherCode|String|unicom|父线路Code，如果没有则为空。

 |
|LineCode|String|cn\_unicom\_shanxi|线路Code。

 |
|LineDisplayName|String|联通\_山西|线路展示名称。

 |
|LineName|String|山西|线路名称。

 |
|RequestId|String|CFDA0830-7D6E-4C13-8632-B57C7EDCF079|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeSupportLines
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSupportLinesResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <RecordLines>
             <RecordLine>
                     <LineCode>cn_unicom_heilongjiang</LineCode>
                     <LineName>黑龙江</LineName>
                     <LineDisplayName>联通_黑龙江</LineDisplayName>
             </RecordLine>
      </RecordLines>
</DescribeSupportLinesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RecordLines":{
		"RecordLine":[
			{
				"LineDisplayName":"默认",
				"LineName":"默认",
				"LineCode":"default"
			},
			{
				"LineDisplayName":"联通",
				"LineName":"联通",
				"LineCode":"unicom"
			},
			{
				"LineDisplayName":"联通_山西",
				"LineName":"山西",
				"LineCode":"cn_unicom_shanxi",
				"FatherCode":"unicom"
			}
		]
	},
	"RequestId":"CFDA0830-7D6E-4C13-8632-B57C7EDCF079"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

