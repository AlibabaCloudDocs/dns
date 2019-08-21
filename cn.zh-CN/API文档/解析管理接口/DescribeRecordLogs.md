# DescribeRecordLogs {#doc_api_Alidns_DescribeRecordLogs .reference}

调用DescribeRecordLogs根据传入参数获取域名的解析操作日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeRecordLogs&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRecordLogs|系统规定参数。取值：**DescribeRecordLogs**。

 |
|DomainName|String|是|example.com|域名名称。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|KeyWord|String|否|test|关键字，按照“%KeyWord%”模式搜索，不区分大小写。

 |
|Lang|String|否|en|语言。

 |
|PageNumber|Long|否|1|当前页数，起始值为**1**，默认为**1**。

 |
|PageSize|Long|否|20|分页查询时设置的每页行数，最大值**100**，默认为**20**。

 |
|StartDate|String|否|2015-12-12T09:23Z|查询的开始时间，格式：**YYYY-MM-DD**。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |
|endDate|String|否|2015-12-12T09:23Z|查询的结束时间，格式：**YYYY-MM-DD**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Long|1|当前页码。

 |
|PageSize|Long|2|本次查询获取的日志数量。

 |
|RecordLogs| | |域名操作日志列表。

 |
|Action|String|暂停解析记录|操作行为

 |
|ActionTime|String|2015-12-12T09:23Z|操作时间

 |
|ActionTimestamp|Long|134514540000|操作时间戳

 |
|ClientIp|String|182.92.253.XX|操作者IP

 |
|Message|String|MX记录 mail 默认 xxxx.top. \( TTL: 600\)|操作消息

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|TotalCount|Long|2|日志列表总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://example.com/?Action=DescribeRecordLogs
&DomainName=example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRecordLogsResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <TotalCount>2</TotalCount>
      <PageNumber>1</PageNumber>
      <PageSize>2</PageSize>
      <RecordLogs>
            <RecordLog>
                  <ActionTime>2015-12-12T09:23Z</ActionTime>
                  <Action>暂停解析记录</Action>
                  <Message>MX记录 mail 默认 xxxx.top. ( TTL: 600)</Message>
                  <ClientIp>182.92.253.20</ClientIp>
            </RecordLog>
            <RecordLog>
                  <ActionTime>2015-12-12T09:23Z</ActionTime>
                  <Action>新增解析记录</Action>
                  <Message>MX记录 mail 默认 xxxx.top. ( TTL: 600)</Message>
                  <ClientIp>182.92.253.20</ClientIp>
            </RecordLog>
      </RecordLogs>
</DescribeRecordLogsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DescribeRecordLogsResponse":{
		"PageNumber":"1",
		"TotalCount":"2",
		"PageSize":"2",
		"RecordLogs":{
			"RecordLog":[
				{
					"Action":"暂停解析记录",
					"Message":"MX记录 mail 默认 xxxx.top. ( TTL: 600)",
					"ActionTime":"2015-12-12T09:23Z",
					"ClientIp":"182.92.253.20"
				},
				{
					"Action":"新增解析记录",
					"Message":"MX记录 mail 默认 xxxx.top. ( TTL: 600)",
					"ActionTime":"2015-12-12T09:23Z",
					"ClientIp":"182.92.253.20"
				}
			]
		},
		"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

