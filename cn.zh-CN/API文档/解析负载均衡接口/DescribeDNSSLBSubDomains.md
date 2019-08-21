# DescribeDNSSLBSubDomains {#doc_api_Alidns_DescribeDNSSLBSubDomains .reference}

调用DescribeDNSSLBSubDomains根据传入参数获取解析负载均衡的子域名列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDNSSLBSubDomains&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDNSSLBSubDomains|系统规定参数。取值：**DescribeDNSSLBSubDomains**。

 |
|DomainName|String|是|example.com|域名名称。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|语言。

 |
|PageNumber|Long|否|1|当前页数，起始值为**1**，默认为**1**。

 |
|PageSize|Long|否|20|分页查询时设置的每页行数，最大值**100**，默认为**20**。

 |
|UserClientIp|String|否|1.1.1.1|用户IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Long|1|当前页码。

 |
|PageSize|Long|1|本次查询获取的子域名数量。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|SlbSubDomains| | |子域名负载均衡结构列表。

 |
|Open|Boolean|true|解析负载均衡状态。

 |
|RecordCount|Long|3|解析记录数量。

 |
|SubDomain|String|www.example.com|子域名名称。

 |
|Type|String|LoadBalancer|类型。

 |
|TotalCount|Long|1|域名分组数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeDNSSLBSubDomains
&DomainName=example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDNSSLBSubDomainsResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <TotalCount>1</TotalCount>
      <PageNumber>1</PageNumber>
      <PageSize>1</PageSize>
      <SlbSubDomains>
            <SlbSubDomain>
                  <SubDomain>www.example.com</SubDomain>
                  <RecordCount>3</RecordCount>
                  <Open>true</Open>
            </SlbSubDomain>
      </SlbSubDomains>
</DescribeDNSSLBSubDomainsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SlbSubDomains":{
		"SlbSubDomain":[
			{
				"Open":true,
				"RecordCount":3,
				"SubDomain":"www.example.com"
			}
		]
	},
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":1,
	"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

