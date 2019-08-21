# DescribeDomainLogs {#doc_api_Alidns_DescribeDomainLogs .reference}

调用DescribeDomainLogs根据传入参数获取域名的操作日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDomainLogs&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainLogs|系统规定参数。取值：**DescribeDomainLogs**。

 |
|GroupId|String|否|2223|域名分组ID。

 |
|KeyWord|String|否|test|关键字，按照“%KeyWord%”模式搜索，不区分大小写。

 |
|Lang|String|否|en|语言。

 |
|PageNumber|Long|否|1|当前页数，起始值为**1**，默认为**1**。

 |
|PageSize|Long|否|20|分页查询时设置的每页行数，最大值**100**，默认为**20**。

 |
|StartDate|String|否|2019-07-04|开始时间。格式：**YYYY-MM-DD**。

 |
|Type|String|否|MX|记录类型。

 |
|UserClientIp|String|否|1.1.1.1|用户IP。

 |
|endDate|String|否|2019-07-04|结束时间。格式：**YYYY-MM-DD**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainLogs| | |域名操作日志列表。

 |
|Action|String|添加|操作行为

 |
|ActionTime|String|2015-12-12T09:23Z|操作时间

 |
|ActionTimestamp|Long|143562300000|操作时间戳

 |
|ClientIp|String|182.92.253.20|操作者IP

 |
|DomainName|String|abc.com|域名名称

 |
|Message|String|到域名解析列表|操作消息

 |
|ZoneId|String|cxfd345sd234|Zone ID

 |
|PageNumber|Long|1|当前页码。

 |
|PageSize|Long|2|本次查询获取的日志数量。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|TotalCount|Long|2|日志列表总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeDomainLogs
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainLogsResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <TotalCount>2</TotalCount>
      <PageNumber>1</PageNumber>
      <PageSize>2</PageSize>
      <DomainLogs>
            <DomainLog>
                  <ActionTime>2015-12-12T09:23Z</ActionTime>
                  <DomainName>abc.com</DomainName>
                  <Action>添加</Action>
                  <Message>到域名解析列表</Message>
                  <ClientIp>182.92.253.20</ClientIp>
            </DomainLog>
            <DomainLog>
                  <ActionTime>2015-12-12T09:23Z</ActionTime>
                  <DomainName>example.com</DomainName>
                  <Action>找回成功</Action>
                  <Message>并添加到域名解析列表</Message>
                  <ClientIp>182.92.253.20</ClientIp>
            </DomainLog>
      </DomainLogs>
</DescribeDomainLogsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DescribeDomainLogsResponse":{
		"PageNumber":"1",
		"TotalCount":"2",
		"PageSize":"2",
		"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
		"DomainLogs":{
			"DomainLog":[
				{
					"Action":"添加",
					"Message":"到域名解析列表",
					"ActionTime":"2015-12-12T09:23Z",
					"ClientIp":"182.92.253.20",
					"DomainName":"abc.com"
				},
				{
					"Action":"找回成功",
					"Message":"并添加到域名解析列表",
					"ActionTime":"2015-12-12T09:23Z",
					"ClientIp":"182.92.253.20",
					"DomainName":"example.com"
				}
			]
		}
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

