# 查询域名的DNSSEC信息

调用DescribeDomainDnssecInfo接口，根据传入参数查询指定域名的DNSSEC信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=DescribeDomainDnssecInfo&type=RPC&version=2015-01-09)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainDnssecInfo|系统规定参数。取值：DescribeDomainDnssecInfo。 |
|DomainName|String|是|example.com|域名名称。 |
|Lang|String|否|en|返回参数语言，仅个别参数生效，例如：地域。默认值为en。可取：en，zh，ja。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Algorithm|String|13|算法类型（如果Dnssec开启则返回）。 |
|Digest|String|C1A0424B97A049F1F9B2EA139CC298533219668164E343BD21203ABC4608C02A|摘要（如果Dnssec开启则返回）。 |
|DigestType|String|SHA256|摘要类型（如果Dnssec开启则返回）。 |
|DomainName|String|example.com|域名名称。 |
|DsRecord|String|example.com. 3600 IN DS 2371 13 2 C1A0424B97A049F1F9B2EA139CC298533219668164E343BD21203ABC4608C02A|DS记录（如果Dnssec开启则返回）。 |
|Flags|String|257 \(KSK\)|标志（如果Dnssec开启则返回）。 |
|KeyTag|String|54931|密钥标签（如果Dnssec开启则返回）。 |
|PublicKey|String|mdsswUyr3DPW132mOi8V9xESWE8jTo0dxCjjnopKl+GqJxpVXckHAeF+KkxLbxILfDLUT0rAK9iUzy1L53eKGQ==|公钥（如果Dnssec开启则返回）。 |
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|唯一请求识别码。 |
|Status|String|ON|Dnssec状态

 -   ON 开启
-   OFF 关闭 |

## 示例

请求示例

```
http(s)://alidns.aliyuncs.com/?Action=DescribeDomainDnssecInfo
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<Status>ON</Status>
<RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
<Digest>C1A0424B97A049F1F9B2EA139CC298533219668164E343BD21203ABC4608C02A</Digest>
<DomainName>example.com</DomainName>
<PublicKey>mdsswUyr3DPW132mOi8V9xESWE8jTo0dxCjjnopKl+GqJxpVXckHAeF+KkxLbxILfDLUT0rAK9iUzy1L53eKGQ==</PublicKey>
<DigestType>SHA256</DigestType>
<DsRecord>example.com. 3600 IN DS 2371 13 2 C1A0424B97A049F1F9B2EA139CC298533219668164E343BD21203ABC4608C02A</DsRecord>
<KeyTag>54931</KeyTag>
<Flags>257 (KSK)</Flags>
<Algorithm>13</Algorithm>
```

`JSON` 格式

```
{
	"Status": "ON",
	"RequestId": "536E9CAD-DB30-4647-AC87-AA5CC38C5382",
	"Digest": "C1A0424B97A049F1F9B2EA139CC298533219668164E343BD21203ABC4608C02A",
	"DomainName": "example.com",
	"PublicKey": "mdsswUyr3DPW132mOi8V9xESWE8jTo0dxCjjnopKl+GqJxpVXckHAeF+KkxLbxILfDLUT0rAK9iUzy1L53eKGQ==",
	"DigestType": "SHA256",
	"DsRecord": "example.com. 3600 IN DS 2371 13 2 C1A0424B97A049F1F9B2EA139CC298533219668164E343BD21203ABC4608C02A",
	"KeyTag": "54931",
	"Flags": "257 (KSK)",
	"Algorithm": "13"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Alidns)查看更多错误码。

