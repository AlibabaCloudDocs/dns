# 设置域名DNSSEC状态

调用SetDomainDnssecStatus设置域名DNSSEC状态

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Alidns&api=SetDomainDnssecStatus&type=RPC&version=2015-01-09)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetDomainDnssecStatus|系统规定参数。取值：SetDomainDnssecStatus。 |
|DomainName|String|是|example.com|域名。 |
|Status|String|是|ON|Dnssec状态：

 -   ON 开启
-   OFF 关闭 |
|Lang|String|否|en|部分返回参数语言。默认值：en。取值范围：en、zh、ja。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|536E9CAD-DB30-4647-AC87-AA5CC38C5382|唯一请求识别码。 |

## 示例

请求示例

```
http(s)://alidns.aliyuncs.com/?Action=SetDomainDnssecStatus
&DomainName=example.com
&Status=ON
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<RequestId>536E9CAD-DB30-4647-AC87-AA5CC38C5382</RequestId>
```

`JSON` 格式

```
{
    "RequestId":"536E9CAD-DB30-4647-AC87-AA5CC38C5382"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Alidns)查看更多错误码。

