# CopyGtmConfig

Copies Global Traffic Manager \(GTM\) configurations.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Alidns&api=CopyGtmConfig&type=RPC&version=2015-01-09)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CopyGtmConfig|The operation that you want to perform. Set the value to CopyGtmConfig. |
|CopyType|String|Yes|INSTANCE|The type of the object that you want to copy. Only the INSTANCE type is supported. |
|SourceId|String|Yes|gtm-cn-0pp1j84v60d|The ID of the source object. Only instance IDs are supported. |
|TargetId|String|Yes|gtm-cn-v0h1gaujg06|The ID of the target object. Only instance IDs are supported. |
|Lang|String|No|en|The language that specific response parameters will use. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|389DFFA3-77A5-4A9E-BF3D-147C6F98A5BA|The ID of the request. |

## Examples

Sample requests

```
http://alidns.aliyuncs.com/?Action=CopyGtmConfig
&SourceId=instance1
&TargetId=instance2
&CopyType=INSTANCE
&<Common request parameters>
```

Sample success responses

`XML` format

```
<RequestId>389DFFA3-77A5-4A9E-BF3D-147C6F98A5BA</RequestId>
```

`JSON` format

```
{
  "RequestId": "389DFFA3-77A5-4A9E-BF3D-147C6F98A5BA"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Alidns).

For a list of error codes, visit the [API Error Center](https://error-center.aliyun.com/status/product/Alidns?spm=a2c4g.11186623.2.17.49253e4bSSu3Kz).

