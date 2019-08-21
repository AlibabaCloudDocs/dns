# DeleteDomainGroup {#doc_api_Alidns_DeleteDomainGroup .reference}

调用DeleteDomainGroup根据传入参数删除域名分组名称。

**说明：** 域名分组中包含的域名数量为0，才能删除域名分组，且默认分组无法删除。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DeleteDomainGroup&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteDomainGroup|系统规定参数。取值：**DeleteDomainGroup**。

 |
|GroupId|String|是|2223|域名分组ID。

 |
|Lang|String|否|en|语言。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GroupName|String|MyGroup|域名分组名称。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DeleteDomainGroup
&GroupId=2223
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteDomainGroupResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <GroupName>MyGroup</GroupName>
</DeleteDomainGroupResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"GroupName":"MyGroup",
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

