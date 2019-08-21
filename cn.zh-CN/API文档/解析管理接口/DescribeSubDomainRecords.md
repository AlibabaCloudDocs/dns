# DescribeSubDomainRecords {#doc_api_Alidns_DescribeSubDomainRecords .reference}

调用DescribeSubDomainRecords根据传入参数获取某个固定子域名的所有解析记录列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeSubDomainRecords&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSubDomainRecords|系统规定参数。取值：**DescribeSubDomainRecords**。

 |
|SubDomain|String|是|www.abc.com|子域名名称。

 例如`www.abc.com`，如果输入的是abc.com，则认为是@.abc.com。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|DomainName|String|否|example.com|域名名称。

 |
|Lang|String|否|en|语言。

 |
|Line|String|否|default|解析线路。

 |
|PageNumber|Long|否|1|当前页数，起始值为**1**，默认为**1**。

 |
|PageSize|Long|否|20|分页查询时设置的每页行数，最大值**500**，默认为**20**。

 |
|Type|String|否|MX|解析记录类型。若不传值，则返回子域名对应的全部解析记录类型。

 解析类型包括\(不区分大小写\)：**A、MX、CNAME、TXT、REDIRECT\_URL、FORWORD\_URL、NS、AAAA、SRV**。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainRecords| | |解析记录列表。

 |
|DomainName|String|example.com|域名名称

 |
|Line|String|default|解析线路

 |
|Locked|Boolean|false|解析记录锁定状态

 |
|Priority|Long|2|MX记录的优先级

 |
|RR|String|www|主机记录

 |
|RecordId|String|9999985|解析记录ID

 |
|Status|String|Enable|解析记录状态

 |
|TTL|Long|600|生存时间

 |
|Type|String|CNAME|记录类型

 |
|Value|String|mail1.hichina.com|记录值

 |
|Weight|Integer|10|负载均衡权重

 |
|PageNumber|Long|1|当前页码。

 |
|PageSize|Long|2|本次查询获取的解析数量。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|TotalCount|Long|2|解析记录总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeSubDomainRecords
&SubDomain=www.abc.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSubDomainRecordsResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <TotalCount>2</TotalCount>
      <PageNumber>1</PageNumber>
      <PageSize>2</PageSize>
      <DomainRecords>
            <Record>
                  <DomainName>example.com</DomainName>
                  <RecordId>9999985</RecordId>
                  <RR>www</RR>
                  <Type>CNAME</Type>
                  <Value>mail1.hichina.com</Value>
                  <Line>default</Line>
                  <TTL>600</TTL>
                  <Status>Enable</Status>
                  <Locked>false</Locked>
                  <Weight>10</Weight>
            </Record>
            <Record>
                  <DomainName>example.com</DomainName>
                  <RecordId>9999986</RecordId>
                  <RR>www</RR>
                  <Type>CNAME</Type>
                  <Value>mail2.hichina.com</Value>
                  <Line>default</Line>
                  <TTL>600</TTL>
                  <Status>Enable</Status>
                  <Locked>false</Locked>
                  <Weight>10</Weight>
            </Record>
      </DomainRecords>
</DescribeSubDomainRecordsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"PageSize":2,
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"DomainRecords":{
		"Record":[
			{
				"RR":"www",
				"Status":"Enable",
				"Value":"mail1.hichina.com",
				"Weight":10,
				"RecordId":"9999985",
				"Type":"CNAME",
				"DomainName":"example.com",
				"Locked":false,
				"Line":"default",
				"TTL":600
			},
			{
				"RR":"www",
				"Status":"Enable",
				"Value":"mail2.hichina.com",
				"Weight":10,
				"RecordId":"9999986",
				"Type":"CNAME",
				"DomainName":"example.com",
				"Locked":false,
				"Line":"default",
				"TTL":600
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

