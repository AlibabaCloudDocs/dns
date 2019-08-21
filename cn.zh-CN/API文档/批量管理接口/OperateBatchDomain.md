# OperateBatchDomain {#doc_api_Alidns_OperateBatchDomain .reference}

调用OperateBatchDomain提交批量管理域名、解析记录的任务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=OperateBatchDomain&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|OperateBatchDomain|系统规定参数。取值：**OperateBatchDomain**。

 |
|DomainRecordInfo.N.Domain|String|否|example.com|域名名称。

 **说明：** 用户提交的数据，最多**1000**条数据，超过1000条的数据会被忽略，不予处理。

 |
|DomainRecordInfo.N.Line|String|否|default|解析线路，默认为default。

 参阅[解析线路枚举](https://help.aliyun.com/document_detail/29807.html?spm=a2c4g.11186623.2.16.35a54681IwK1zN)。

 |
|DomainRecordInfo.N.Priority|Integer|否|1|MX优先级。

 记录类型为MX时必需。

 |
|DomainRecordInfo.N.Rr|String|否|zhaohui|主机记录。

 **说明：** 批量操作类型为**RR\_ADD**或**RR\_DEL**时必需。

 |
|DomainRecordInfo.N.Ttl|Integer|否|12|生效时间。

 |
|DomainRecordInfo.N.Type|String|否|MX|记录类型。有关云解析DNS支持的记录类型，请参阅[解析记录类型格式](https://help.aliyun.com/document_detail/29805.html?spm=a2c4g.11186623.2.17.35a54681JtREuC)。

 **说明：** 批量操作类型为**RR\_ADD**或**RR\_DEL**时必需。

 |
|DomainRecordInfo.N.Value|String|否|fd87da3c4528844d45af39200155a905|记录值。

 **说明：** 批量操作类型为**RR\_ADD**或**RR\_DEL**时必需。

 |
|Lang|String|否|en|语言。

 |
|Type|String|否|DOMAIN\_ADD|批量操作类型，取值：

 -   **DOMAIN\_ADD**：批量添加域名
-   **DOMAIN\_DEL**：批量删除域名
-   **RR\_ADD**：批量添加解析
-   **RR\_DEL**：批量删除解析

 |
|UserClientIp|String|否|1.1.1.1|用户IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|75446CC1-FC9A-4595-8D96-089D73D7A63D|请求ID。

 |
|TaskId|Long|345345|任务ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=OperateBatchDomain
&DomainRecordInfo.1.Type=MX
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<OperateBatchDomainResponse>
      <RequestId>75446CC1-FC9A-4595-8D96-089D73D7A63D</RequestId>
      <TaskId>345345</TaskId>
</OperateBatchDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"75446CC1-FC9A-4595-8D96-089D73D7A63D",
	"TaskId":"345345"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

