# DescribeBatchResultCount {#doc_api_Alidns_DescribeBatchResultCount .reference}

调用DescribeBatchResultCount查询一次批量操作任务的执行结果。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeBatchResultCount&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeBatchResultCount|系统规定参数。取值：**DescribeBatchResultCount**。

 |
|BatchType|String|否|DOMAIN\_ADD|批量操作类型，取值：

 -   **DOMAIN\_ADD**：批量添加域名
-   **DOMAIN\_DEL**：批量删除域名
-   **RR\_ADD**：批量添加解析
-   **RR\_DEL**：批量删除解析

 |
|Lang|String|否|en|用户语言。

 |
|TaskId|Long|否|123456|任务ID。

 如果TaskId不为空，返回TaskId对应任务的执行结果；如果TaskId为空，返回最后一次任务的执行结果。

 |
|UserClientIp|String|否|1.1.1.1|用户端 IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BatchType|String|DOMAIN\_ADD|批量操作类型。

 |
|FailedCount|Integer|2|处理失败的域名或解析记录总数。

 |
|Reason|String|failed\_reason|处理失败的原因。

 |
|RequestId|String|75446CC1-FC9A-4595-8D96-089D73D7A63D|请求ID。

 |
|Status|Integer|0|任务状态，取值：

 -   **-1**：无已提交的导入域名或解析任务
-   **0**：处理中
-   **1**：已完成
-   **2**：已失败

 |
|SuccessCount|Integer|2|处理成功的域名或解析记录总数。

 |
|TaskId|Long|123456|最后一次任务ID。

 |
|TotalCount|Integer|4|批量处理的记录总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeBatchResultCount
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeBatchResultCountResponse>
      <RequestId>75446CC1-FC9A-4595-8D96-089D73D7A63D</RequestId>
      <Status>0</Status>
</DescribeBatchResultCountResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Status":"0",
	"RequestId":"75446CC1-FC9A-4595-8D96-089D73D7A63D"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

