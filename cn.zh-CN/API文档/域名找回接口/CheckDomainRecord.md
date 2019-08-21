# CheckDomainRecord {#doc_api_Alidns_CheckDomainRecord .reference}

调用CheckDomainRecord检查指定的解析记录在权威DNS是否存在（生效）。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=CheckDomainRecord&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CheckDomainRecord|系统规定参数。取值：**CheckDomainRecord**。

 |
|DomainName|String|是|example.com|域名名称

 |
|RR|String|是|zhaohui|主机记录

 |
|Type|String|是|TXT|记录类型

 |
|Value|String|是|fd87da3c4528844d45af39200155a905|记录值

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID

 |
|Lang|String|否|en|语言

 |
|UserClientIp|String|否|1.1.1.1|用户IP

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|IsExist|Boolean|true|是否存在解析记录。取值：

 -   **true**：已存在
-   **false**：不存在

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=CheckDomainRecord
&DomainName=example.com
&RR=zhaohui
&Type=TXT
&Value=fd87da3c4528844d45af39200155a905
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CheckDomainRecordResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <IsExist>true</IsExist>
</CheckDomainRecordResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"IsExist":false
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

