# DeleteSubDomainRecords {#doc_api_Alidns_DeleteSubDomainRecords .reference}

调用DeleteSubDomainRecords根据传入参数删除主机记录对应的解析记录。

如果被删除的解析记录中存在锁定解析，则该锁定解析不会被删除。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DeleteSubDomainRecords&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteSubDomainRecords|系统规定参数。取值：**DeleteSubDomainRecords**。

 |
|DomainName|String|是|example.com|域名名称。

 |
|RR|String|是|www|主机记录。

 如果要解析@.exmaple.com，主机记录要填写”@”，而不是空。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|语言。

 |
|Type|String|否|A|解析记录类型。如果不填写，则返回子域名对应的全部解析记录类型。

 解析类型包括\(不区分大小写\)：**A、MX、CNAME、TXT、REDIRECT\_URL、FORWORD\_URL、NS、AAAA、SRV**。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RR|String|www|主机记录。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|TotalCount|String|1|被删除的解析记录总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DeleteSubDomainRecords
&DomainName=example.com
&RR=www
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteSubDomainRecordsResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <RR>www</RR>
      <TotalCount>1</TotalCount>
</DeleteSubDomainRecordsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RR":"www",
	"TotalCount":"1",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

