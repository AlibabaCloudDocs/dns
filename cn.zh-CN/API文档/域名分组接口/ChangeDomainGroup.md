# ChangeDomainGroup {#doc_api_Alidns_ChangeDomainGroup .reference}

调用ChangeDomainGroup根据传入参数将域名从原分组更换到新分组。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=ChangeDomainGroup&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ChangeDomainGroup|系统规定参数。取值：**ChangeDomainGroup**。

 |
|DomainName|String|是|abc.com|域名名称。

 |
|GroupId|String|否|2223|目标域名分组ID。

 |
|Lang|String|否|en|语言。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GroupId|String|2223|目标域名分组ID。

 |
|GroupName|String|MyGroup|目标域名分组名称。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=ChangeDomainGroup
&DomainName=abc.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ChangeDomainGroupResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <GroupId>2223</GroupId>
      <GroupName>MyGroup</GroupName>
</ChangeDomainGroupResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"GroupName":"MyGroup",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"GroupId":"2223"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

