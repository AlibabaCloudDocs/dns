# UpdateDomainGroup {#doc_api_Alidns_UpdateDomainGroup .reference}

调用UpdateDomainGroup根据传入参数修改域名分组名称。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=UpdateDomainGroup&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|UpdateDomainGroup|系统规定参数。取值：**UpdateDomainGroup**。

 |
|GroupId|String|是|2223|域名分组ID。

 |
|GroupName|String|是|NewName|域名分组新名称。

 |
|Lang|String|否|en|语言。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GroupId|String|2223|域名分组ID。

 |
|GroupName|String|NewName|域名分组名称。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=UpdateDomainGroup
&GroupId=2223
&GroupName=NewName
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateDomainGroupResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <GroupId>2223</GroupId>
      <GroupName>NewName</GroupName>
</UpdateDomainGroupResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"GroupName":"NewName",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"GroupId":"2223"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

