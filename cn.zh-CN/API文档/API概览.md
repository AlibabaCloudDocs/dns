# API概览 {#doc_1399275 .concept}

云解析DNS提供以下相关API接口。

## 域名管理接口 {#section_2ty_emo_syb .section}

|API|描述|
|---|--|
|[AddDomain](cn.zh-CN/API文档/域名管理接口/AddDomain.md)|调用AddDomain根据传入参数添加域名。|
|[DeleteDomain](cn.zh-CN/API文档/域名管理接口/DeleteDomain.md)|调用DeleteDomain根据传入参数删除域名。|
|[DescribeDomains](cn.zh-CN/API文档/域名管理接口/DescribeDomains.md)|调用DescribeDomains根据传入参数查询该用户的域名列表。|
|[DescribeDomainInfo](cn.zh-CN/API文档/域名管理接口/DescribeDomainInfo.md)|调用DescribeDomainInfo根据传入参数查询指定域名的信息。|
|[ModifyHichinaDomainDNS](cn.zh-CN/API文档/域名管理接口/ModifyHichinaDomainDNS.md)|调用ModifyHichinaDomainDNS根据传入参数修改域名DNS服务器名称。|
|[GetMainDomainName](cn.zh-CN/API文档/域名管理接口/GetMainDomainName.md)|调用GetMainDomainName通过输入的参数，获取主域名名称。|
|[DescribeDomainLogs](cn.zh-CN/API文档/域名管理接口/DescribeDomainLogs.md)|调用DescribeDomainLogs根据传入参数获取域名的操作日志。|

## 云解析产品管理接口 {#section_eln_sjq_hzg .section}

|API|描述|
|---|--|
|[DescribeDnsProductInstances](cn.zh-CN/API文档/云解析产品管理接口/DescribeDnsProductInstances.md)|调用DescribeDnsProductInstances根据传入参数获取云解析收费版本产品列表。|
|[ChangeDomainOfDnsProduct](cn.zh-CN/API文档/云解析产品管理接口/ChangeDomainOfDnsProduct.md)|调用ChangeDomainOfDnsProduct更换云解析产品绑定的域名。|

## 域名分组接口 {#section_brs_dz4_za2 .section}

|API|描述|
|---|--|
|[AddDomainGroup](cn.zh-CN/API文档/域名分组接口/AddDomainGroup.md)|调用AddDomainGroup根据传入参数添加域名分组。|
|[UpdateDomainGroup](cn.zh-CN/API文档/域名分组接口/UpdateDomainGroup.md)|调用UpdateDomainGroup根据传入参数修改域名分组名称。|
|[DeleteDomainGroup](cn.zh-CN/API文档/域名分组接口/DeleteDomainGroup.md)|调用DeleteDomainGroup根据传入参数删除域名分组名称。|
|[ChangeDomainGroup](cn.zh-CN/API文档/域名分组接口/ChangeDomainGroup.md)|调用ChangeDomainGroup根据传入参数将域名从原分组更换到新分组。|
|[DescribeDomainGroups](cn.zh-CN/API文档/域名分组接口/DescribeDomainGroups.md)|调用DescribeDomainGroups根据传入参数获取所有分组列表。|

## 域名找回接口 {#section_2ug_uvx_nb0 .section}

|API|描述|
|---|--|
|[CheckDomainRecord](cn.zh-CN/API文档/域名找回接口/CheckDomainRecord.md)|调用CheckDomainRecord检查指定的解析记录在权威DNS是否存在（生效）。|

## 解析管理接口 {#section_vfx_auk_9sv .section}

|API|描述|
|---|--|
|[DescribeDomainRecords](cn.zh-CN/API文档/解析管理接口/DescribeDomainRecords.md)|调用DescribeDomainRecords根据传入参数获取指定主域名的所有解析记录列表。|
|[DescribeDomainRecordInfo](cn.zh-CN/API文档/解析管理接口/DescribeDomainRecordInfo.md)|调用DescribeDomainRecordInfo获取解析记录的详细信息。|
|[DescribeSubDomainRecords](cn.zh-CN/API文档/解析管理接口/DescribeSubDomainRecords.md)|调用DescribeSubDomainRecords根据传入参数获取某个固定子域名的所有解析记录列表。|
|[AddDomainRecord](cn.zh-CN/API文档/解析管理接口/AddDomainRecord.md)|调用AddDomainRecord根据传入参数添加解析记录。|
|[DeleteDomainRecord](cn.zh-CN/API文档/解析管理接口/DeleteDomainRecord.md)|调用DeleteDomainRecord根据传入参数删除解析记录。|
|[UpdateDomainRecord](cn.zh-CN/API文档/解析管理接口/UpdateDomainRecord.md)|调用UpdateDomainRecord根据传入参数修改解析记录。|
|[DeleteSubDomainRecords](cn.zh-CN/API文档/解析管理接口/DeleteSubDomainRecords.md)|调用DeleteSubDomainRecords根据传入参数删除主机记录对应的解析记录。|
|[SetDomainRecordStatus](cn.zh-CN/API文档/解析管理接口/SetDomainRecordStatus.md)|调用SetDomainRecordStatus根据传入参数设置解析记录状态。|
|[DescribeRecordLogs](cn.zh-CN/API文档/解析管理接口/DescribeRecordLogs.md)|调用DescribeRecordLogs根据传入参数获取域名的解析操作日志。|
|[DescribeSupportLines](cn.zh-CN/API文档/解析管理接口/DescribeSupportLines.md)|调用DescribeSupportLines查询云解析支持的所有线路列表。|

## 请求量统计接口 {#section_uy2_62t_h4g .section}

|API|描述|
|---|--|
|[DescribeDomainStatisticsSummary](cn.zh-CN/API文档/请求量统计接口/DescribeDomainStatisticsSummary.md)|调用DescribeDomainStatisticsSummary查询用户账号下所有付费域名的请求量列表。|
|[DescribeRecordStatisticsSummary](cn.zh-CN/API文档/请求量统计接口/DescribeRecordStatisticsSummary.md)|调用DescribeRecordStatisticsSummary查询指定域名下的全部子域名的请求量统计。|
|[DescribeRecordStatistics](cn.zh-CN/API文档/请求量统计接口/DescribeRecordStatistics.md)|调用DescribeRecordStatistics查询指定子域名请求量的实时数据。|
|[DescribeDomainStatistics](cn.zh-CN/API文档/请求量统计接口/DescribeDomainStatistics.md)|调用DescribeDomainStatistics查询指定主域名请求量的实时数据。|

## 解析负载均衡接口 {#section_2dz_byi_tkc .section}

|API|描述|
|---|--|
|[SetDNSSLBStatus](cn.zh-CN/API文档/解析负载均衡接口/SetDNSSLBStatus.md)|调用SetDNSSLBStatus根据传入参数开关解析负载均衡。|
|[DescribeDNSSLBSubDomains](cn.zh-CN/API文档/解析负载均衡接口/DescribeDNSSLBSubDomains.md)|调用DescribeDNSSLBSubDomains根据传入参数获取解析负载均衡的子域名列表。|
|[UpdateDNSSLBWeight](cn.zh-CN/API文档/解析负载均衡接口/UpdateDNSSLBWeight.md)|调用UpdateDNSSLBWeight根据传入参数修改解析负载均衡的权重。|

## 批量管理接口 {#section_akz_qjr_uj9 .section}

|API|描述|
|---|--|
|[OperateBatchDomain](cn.zh-CN/API文档/批量管理接口/OperateBatchDomain.md)|调用OperateBatchDomain提交批量管理域名、解析记录的任务。|
|[DescribeBatchResultCount](cn.zh-CN/API文档/批量管理接口/DescribeBatchResultCount.md)|调用DescribeBatchResultCount查询一次批量操作任务的执行结果。|
|[DescribeBatchResultDetail](cn.zh-CN/API文档/批量管理接口/DescribeBatchResultDetail.md)|调用DescribeBatchResultDetail查询批量处理结果的详细信息。|

