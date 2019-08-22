# DescribeDomains {#doc_api_Alidns_DescribeDomains .reference}

调用DescribeDomains根据传入参数查询该用户的域名列表。

-   可以指定页码（PageNumber）和每页的数量（PageSize）来获取域名列表。
-   可以指定域名的关键字（KeyWord）来查询含有该关键字的域名列表。
-   域名列表的默认排序方式是按照域名添加的时间从新到旧排序的。
-   可以指定域名分组的ID（GroupId），默认为全部分组。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDomains&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomains|系统规定参数。取值：**DescribeDomains**。

 |
|GroupId|String|否|2223|域名分组ID，如果不填写则默认为全部分组。

 |
|KeyWord|String|否|com|关键字，按照“%KeyWord%”模式搜索，不区分大小写。

 |
|Lang|String|否|en|用户语言。

 |
|PageNumber|Long|否|1|当前页数，起始值为**1**，默认为**1**。

 |
|PageSize|Long|否|20|分页查询时设置的每页行数，最大值**100**，默认为**20**。

 |
|ResourceGroupId|String|否|rg-resourcegroupid01|资源组ID。

 |
|SearchMode|String|否|LIKE|搜索模式。取值：

 -   **LIKE**：模糊搜索
-   **EXACT**：精确搜索

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Domains| | |本次获取的域名列表。

 |
|AliDomain|Boolean|true|是否为阿里云万网域名。

 |
|DnsServers| |\{"DnsServer": \["ns1.alidns.com","ns2.alidns.com"\]\}|域名在解析系统中的DNS列表。

 |
|DomainId|String|00efd71a-770e-4255-b54e-6fe5659baffe|域名ID。

 |
|DomainName|String|abc.com|域名名称。

 |
|GroupId|String|2223|域名分组ID。

 |
|GroupName|String|mygroup|域名分组名称。

 |
|InstanceEndTime|String|2020-03-14T16:00Z|实例的到期时间。

 |
|InstanceExpired|Boolean|false|实例是否过期。

 |
|InstanceId|String|i-7bg|云解析产品ID。

 |
|PunyCode|String|abc.com|中文域名的punycode码，英文域名返回为空。

 |
|RecordCount|Long|100|域名含有的解析记录条数。

 |
|RegistrantEmail|String|test@example.com|注册人邮箱。

 |
|Remark|String|remark|备注。

 |
|VersionCode|String|version\_enterprise\_basic|云解析版本Code。

 |
|VersionName|String|企业标准版|云解析产品名称。

 |
|PageNumber|Long|1|当前页码。

 |
|PageSize|Long|2|本次查询获取的域名数量。

 |
|RequestId|String|68386699-8B9E-4D5B-BC4C-75A28F6C2A00|请求ID。

 |
|TotalCount|Long|2|域名列表总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeDomains
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainsResponse>
      <RequestId>6393C3A8-B611-42F2-AFA6-F080FC45D5D0</RequestId>
      <TotalCount>2</TotalCount>
      <PageNumber>1</PageNumber>
      <PageSize>2</PageSize>
      <Domains>
            <Domain>
                  <DomainId>00efd71a-770e-4255-b54e-6fe5659baffe</DomainId>
                  <DomainName>abc.com</DomainName>
                  <AliDomain>true</AliDomain>
                  <GroupId>2223</GroupId>
                  <PunyCode>abc.com</PunyCode>
                  <InstanceId>i-7bg</InstanceId>
                  <VersionCode>version1</VersionCode>
                  <DnsServers>
                        <DnsServer>dns1.hichina.com</DnsServer>
                        <DnsServer>dns2.hichina.com</DnsServer>
                  </DnsServers>
            </Domain>
            <Domain>
                  <DomainId>00efd71a-770e-4255-b54e-6fe5659baffe</DomainId>
                  <DomainName>实例.com</DomainName>
                  <AliDomain>false</AliDomain>
                  <GroupId>2223</GroupId>
                  <PunyCode>xn--fsq270a.com</PunyCode>
                  <InstanceId>i-7bk</InstanceId>
                  <VersionCode>version2</VersionCode>
                  <DnsServers>
                        <DnsServer>dns1.hichina.com</DnsServer>
                        <DnsServer>dns2.hichina.com</DnsServer>
                  </DnsServers>
            </Domain>
      </Domains>
</DescribeDomainsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"PageSize":2,
	"RequestId":"68386699-8B9E-4D5B-BC4C-75A28F6C2A00",
	"Domains":{
		"Domain":[
			{
				"PunyCode":"abc.com",
				"VersionCode":"version1",
				"InstanceId":"i-7bg",
				"AliDomain":"true",
				"DomainName":"abc.com",
				"DomainId":"00efd71a-770e-4255-b54e-6fe5659baffe",
				"DnsServers":{
					"DnsServer":[
						"ns1.alidns.com",
						"ns2.alidns.com"
					]
				},
				"GroupId":"2223"
			},
			{
				"PunyCode":"xn--fsq270a.com",
				"VersionCode":"version2",
				"InstanceId":"i-7bk",
				"AliDomain":"false",
				"DomainName":"实例.com",
				"DomainId":"00efd71a-770e-4255-b54e-6fe5659baffe",
				"DnsServers":{
					"DnsServer":[
						"ns1.alidns.com",
						"ns2.alidns.com"
					]
				},
				"GroupId":"2223"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

