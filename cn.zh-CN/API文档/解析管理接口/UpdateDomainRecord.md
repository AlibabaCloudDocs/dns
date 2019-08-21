# UpdateDomainRecord {#doc_api_Alidns_UpdateDomainRecord .reference}

调用UpdateDomainRecord根据传入参数修改解析记录。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=UpdateDomainRecord&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|UpdateDomainRecord|系统规定参数。取值：**UpdateDomainRecord**。

 |
|RR|String|是|www|主机记录。

 如果要解析@.exmaple.com，主机记录要填写”@”，而不是空。

 |
|RecordId|String|是|9999985|解析记录的ID。

 |
|Type|String|是|A|解析记录类型，参见[解析记录类型格式](https://help.aliyun.com/document_detail/29805.html?spm=a2c4g.11186623.2.20.2cee2846MZb2I3)。

 |
|Value|String|是|202.106.0.20|记录值。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|语言。

 |
|Line|String|否|default|解析线路，默认为**default**。

 参见[解析线路枚举](https://help.aliyun.com/document_detail/29807.html?spm=a2c4g.11186623.2.22.2cee2846MZb2I3)。

 |
|Priority|Long|否|1|MX记录的优先级，取值范围：`[1,10]`。

 记录类型为MX记录时，此参数必需。

 |
|TTL|Long|否|600|解析生效时间，默认为600秒（10分钟）。

 参见[TTL定义说明](https://help.aliyun.com/document_detail/29806.html?spm=a2c4g.11186623.2.21.2cee2846MZb2I3)。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RecordId|String|9999985|解析记录的ID。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=UpdateDomainRecord
&RecordId=9999985
&RR=www
&Type=A
&Value=202.106.0.20
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateDomainRecordResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <RecordId>9999985</RecordId>
 </UpdateDomainRecordResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RecordId":"9999985",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

