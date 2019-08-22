# DescribeDnsProductInstances {#doc_api_Alidns_DescribeDnsProductInstances .reference}

调用DescribeDnsProductInstances根据传入参数获取云解析收费版本产品列表。

**说明：** **如果返回参数中未包含域名，则表示该云解析产品尚未绑定任何域名。**

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDnsProductInstances&type=RPC&version=2015-01-09)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDnsProductInstances|系统规定参数。取值：**DescribeDnsProductInstances**。

 |
|AccessKeyId|String|否|your\_accesskey\_id|您的AccessKey ID。

 |
|Lang|String|否|en|语言。

 |
|PageNumber|Long|否|1|当前页数，起始值为**1**，默认为**1**。

 |
|PageSize|Long|否|20|分页查询时设置的每页行数，最大值**100**，默认为**20**。

 |
|UserClientIp|String|否|1.1.1.1|用户端IP。

 |
|VersionCode|String|否|version1|云解析产品code。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DnsProducts| | |本次获取的云解析产品列表。

 |
|BindCount|Long|3|域名更换次数（次）

 |
|BindDomainCount|Long|5|绑定域名数（个）

 |
|BindDomainUsedCount|Long|3|已绑定域名数（个）

 |
|BindUsedCount|Long|1|已使用更换次数（次）

 |
|DDosDefendFlow|Long|50|DNS防护流量（G）

 |
|DDosDefendQuery|Long|50|DNS防护QPS（WQ/s）

 |
|DnsSLBCount|Long|15|A记录负载均衡数量（个）

 |
|DnsSecurity|String|no|DNS安全。取值：

 -   **no**：不需要
-   **basic**：dns攻击基础防御
-   **advenced**：dns攻击全力防御

 |
|Domain|String|abc.com|绑定域名

 |
|EndTime|String|2015-12-12T09:23Z|到期时间

 |
|EndTimestamp|Long|1474335170000|到期时间戳

 |
|Gslb|Boolean|true|是否允许GSLB

 |
|ISPLines|String|电信、移动、联通、教育网|运营商线路列表

 |
|ISPRegionLines|String|电信（省份）、移动（省份）、联通（省份）、教育网（省份）|运营商线路细分列表

 |
|InBlackHole|Boolean|false|域名是否处于黑洞状态

 |
|InClean|Boolean|false|域名是否处于清洗状态

 |
|InstanceId|String|i-8fj|云解析产品ID

 |
|MonitorFrequency|Long|50|监控频率（单位:分钟）

 |
|MonitorNodeCount|Long|5|监控节点个数（个）

 |
|MonitorTaskCount|Long|2|监控任务数（个）

 |
|OverseaDDosDefendFlow|Long|1|海外DNS防护（G）

 |
|OverseaLine|String|海外大洲|海外线路

 |
|RegionLines|Boolean|true|是否允许地域线路

 |
|SearchEngineLines|String|搜索引擎、谷歌、百度、必应|搜索引擎线路列表

 |
|StartTime|String|2015-12-12T09:23Z|购买时间

 |
|StartTimestamp|Long|1474335170000|购买时间戳

 |
|SubDomainLevel|Long|6|子域名级别（个）

 |
|TTLMinValue|Long|10|最小TTL值（秒）

 |
|URLForwardCount|Long|20|URL转发数量（个）

 |
|VersionCode|String|version1|云解析产品code

 |
|VersionName|String|企业旗舰版|云解析产品名称

 |
|PageNumber|Long|1|当前页码。

 |
|PageSize|Long|2|本次查询获取的域名数量。

 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|请求ID。

 |
|TotalCount|Long|2|域名列表总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://alidns.aliyuncs.com/?Action=DescribeDnsProductInstances
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDnsProductInstancesResponse>
      <RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
      <TotalCount>1</TotalCount>
      <PageNumber>1</PageNumber>
      <PageSize>2</PageSize>
      <DnsProducts>
            <DnsProduct>
                  <InstanceId>i-8fj</InstanceId>
                  <StartTime>2015-12-12T09:23Z</StartTime>
                  <EndTime>2016-12-12T09:23Z</EndTime>
                  <Domain>abc.com</Domain>
                  <BindCount>3</BindCount>
                  <BindUsedCount>1</BindUsedCount>
                  <TTLMinValue>10</TTLMinValue>
                  <SubDomainLevel>6</SubDomainLevel>
                  <DnsSLBCount>15</DnsSLBCount>
                  <URLForwardCount>20</URLForwardCount>
                  <DDosDefendFlow>50</DDosDefendFlow>
                  <DDosDefendQuery>50</DDosDefendQuery>
                  <OverseaDDosDefendFlow>1</OverseaDDosDefendFlow>
                  <SearchEngineLines>搜索引擎、谷歌、百度、必应</SearchEngineLines>
                  <ISPLines>电信、移动、联通、教育网</ISPLines>
                  <ISPRegionLines>电信（省份）、移动（省份）、联通（省份）、教育网（省份）</ISPRegionLines>
                  <OverseaLine>海外大洲</OverseaLine>
            </DnsProduct>
      </DnsProducts>
</DescribeDnsProductInstancesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DescribeDnsProductInstancesResponse":{
		"PageNumber":"1",
		"TotalCount":"1",
		"PageSize":"2",
		"RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382",
		"DnsProducts":{
			"DnsProduct":{
				"DnsSLBCount":"15",
				"ISPRegionLines":"电信（省份）、移动（省份）、联通（省份）、教育网（省份）",
				"Domain":"abc.com",
				"InstanceId":"i-8fj",
				"DDosDefendQuery":"50",
				"URLForwardCount":"20",
				"BindUsedCount":"1",
				"BindCount":"3",
				"OverseaLine":"海外大洲",
				"DDosDefendFlow":"50",
				"OverseaDDosDefendFlow":"1",
				"ISPLines":"电信、移动、联通、教育网",
				"TTLMinValue":"10",
				"SubDomainLevel":"6",
				"EndTime":"2016-12-12T09:23Z",
				"StartTime":"2015-12-12T09:23Z",
				"SearchEngineLines":"搜索引擎、谷歌、百度、必应"
			}
		}
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Alidns)查看更多错误码。

