# DescribeBatchResultDetail {#doc_api_Alidns_DescribeBatchResultDetail .reference}

调用DescribeBatchResultDetail查询批量处理结果的详细信息。

 **前提条件：请在批量任务执行完成后，再调用此接口。** 

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeBatchResultDetail&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeBatchResultDetail|系统规定参数。取值：**DescribeBatchResultDetail**。

 |
|BatchType|String|否|DOMAIN\_ADD|批量操作类型。取值：

 -   **DOMAIN\_ADD**：批量添加域名
-   **DOMAIN\_DEL**：批量删除域名
-   **RR\_ADD**：批量添加解析
-   **RR\_DEL**：批量删除解析

 |
|Lang|String|否|en|用户语言。

 |
|PageNumber|Integer|否|1|当前页码，默认值为**1**。

 |
|PageSize|Integer|否|20|分页查询时每页设置的大小。

 |
|TaskId|Long|否|83618818|任务ID。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BatchResultDetails| | |批量处理结果的详细信息。

 |
|BatchType|String|DOMAIN\_ADD|批量操作类型。

 |
|Domain|String|abc.com|域名。

 |
|Line|String|default|线路代码。

 |
|NewRr|String|demo-batch-7|新的主机记录。

 |
|NewValue|String|1.1.1.0|新的记录值。

 |
|OperateDateStr|String|2019-08-22 18:02:58|处理时间。

 |
|Priority|String|10|MX优先级。

 |
|Reason|String|内部异常|执行失败的原因。

 |
|RecordId|String|123456789|解析记录的ID。

 |
|Remark|String|remark|解析记录备注。

 |
|Rr|String|www|主机记录。

 |
|RrStatus|String|暂停|解析记录状态。

 |
|Status|Boolean|true|执行结果。**true**代表成功，**false**代表失败。

 |
|Ttl|String|600|生效时间。

 |
|Type|String|A|域名解析类型。

 |
|Value|String|202.106.0.XX|记录值。

 |
|PageNumber|Long|1|当前页码。

 |
|PageSize|Long|10|分页大小。

 |
|RequestId|String|75446CC1-FC9A-4595-8D96-089D73D7A63D|请求ID。

 |
|TotalCount|Long|1|记录总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeBatchResultDetail
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeBatchResultDetailResponse>
      <RequestId>75446CC1-FC9A-4595-8D96-089D73D7A63D</RequestId>
      <BatchResultDetail>
            <Domain>abc.com</Domain>
            <Status>true</Status>
      </BatchResultDetail>
</DescribeBatchResultDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"75446CC1-FC9A-4595-8D96-089D73D7A63D",
	"BatchResultDetail":{
		"Status":"true",
		"Domain":"abc.com"
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

