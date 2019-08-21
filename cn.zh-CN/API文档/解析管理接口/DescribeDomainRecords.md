# DescribeDomainRecords {#doc_api_Alidns_DescribeDomainRecords .reference}

调用DescribeDomainRecords根据传入参数获取指定主域名的所有解析记录列表。

-   查询可以指定域名（DomainName）、页码（PageNumber）和每页的数量（PageSize）来获取域名的解析列表。
-   查询可以指定解析记录的主机记录关键字（RRKeyWord）、解析类型关键字（TypeKeyWord）或者记录值的关键字（ValueKeyWord）来查询含有该关键字的解析列表。
-   解析列表的默认排序方式是按照解析添加的时间从新到旧排序的。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDomainRecords&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainRecords|系统规定参数。取值：**DescribeDomainRecords**。

 |
|DomainName|String|是|example.com|域名名称。

 |
|Direction|String|否|描述|域名描述。

 |
|GroupId|Long|否|2223|域名分组ID。

 |
|KeyWord|String|否|test|关键字。

 |
|Lang|String|否|en|语言。

 |
|Line|String|否|default|解析线路，默认为**default**。

 参见[解析线路枚举](https://help.aliyun.com/document_detail/29807.html?spm=a2c4g.11186623.2.22.2cee2846MZb2I3)。

 |
|OrderBy|String|否|default|排序方式。按照解析添加的时间从新到旧排序。

 |
|PageNumber|Long|否|1|当前页数，起始值为**1**，默认为**1**。

 |
|PageSize|Long|否|20|分页查询时设置的每页行数，最大值**500**，默认为**20**。

 |
|RRKeyWord|String|否|www|主机记录的关键字，按照“%RRKeyWord%”模式搜索，不区分大小写。

 |
|SearchMode|String|否|LIKE|搜索模式。

 |
|Status|String|否|Enable|解析记录状态，取值：**Enable/Disable**。

 |
|Type|String|否|A|解析记录类型，参见[解析记录类型格式](https://help.aliyun.com/document_detail/29805.html?spm=a2c4g.11186623.2.20.2cee2846MZb2I3)。

 |
|TypeKeyWord|String|否|MX|解析类型的关键字，按照全匹配搜索，不区分大小写。

 |
|ValueKeyWord|String|否|com|记录值的关键字，按照“%ValueKeyWord%”模式搜索，不区分大小写。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainRecords| | |解析记录列表。

 |
|DomainName|String|example.com|域名名称。

 |
|Line|String|default|解析线路。

 |
|Locked|Boolean|false|当前解析记录锁定状态。

 |
|Priority|Long|5|MX记录的优先级。

 |
|RR|String|www|主机记录。

 |
|RecordId|String|9999985|解析记录ID。

 |
|Remark|String|备注|备注。

 |
|Status|String|Enable|当前的解析记录状态。

 |
|TTL|Long|600|生存时间。

 |
|Type|String|MX|记录类型。

 |
|Value|String|mail1.hichina.com|记录值。

 |
|Weight|Integer|2|负载均衡权重。

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

http(s)://alidns.aliyuncs.com/?Action=DescribeDomainRecords
&DomainName=example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainRecordsResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <TotalCount>2</TotalCount>
      <PageNumber>1</PageNumber>
      <PageSize>2</PageSize>
      <DomainRecords>
            <Record>
                  <DomainName>example.com</DomainName>
                  <RecordId>9999985</RecordId>
                  <RR>www</RR>
                  <Type>MX</Type>
                  <Value>mail1.hichina.com</Value>
                  <Line>default</Line>
                  <Priority>5</Priority>
                  <TTL>600</TTL>
                  <Status>Enable</Status>
                  <Locked>false</Locked>
            </Record>
            <Record>
                  <DomainName>example.com</DomainName>
                  <RecordId>9999986</RecordId>
                  <RR>www</RR>
                  <Type>MX</Type>
                  <Value>mail2.hichina.com</Value>
                  <Line>default</Line>
                  <Priority>10</Priority>
                  <TTL>600</TTL>
                  <Status>Enable</Status>
                  <Locked>false</Locked>
            </Record>
      </DomainRecords>
</DescribeDomainRecordsResponse>
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
				"RecordId":"9999985",
				"Type":"MX",
				"DomainName":"example.com",
				"Locked":false,
				"Line":"default",
				"TTL":600,
				"Priority":5
			},
			{
				"RR":"www",
				"Status":"Enable",
				"Value":"mail2.hichina.com",
				"RecordId":"9999986",
				"Type":"MX",
				"DomainName":"example.com",
				"Locked":false,
				"Line":"default",
				"TTL":600,
				"Priority":10
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

