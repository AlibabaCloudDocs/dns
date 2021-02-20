通过API新购、续费、升级云解析实例 
=======================================

本文主要介绍通过API对云解析付费实例进行新购、续费、自动续费、升级等操作。Demo中部分参数值仅为参考，实际调用时，请传入真实数据。如：Domain、InstanceId。

SDK 
------------------------

* **Maven依赖** ：

  




    <dependencies>
        <dependency>
            <groupId>com.aliyun</groupId>
            <artifactId>aliyun-java-sdk-bssopenapi</artifactId>
            <version>1.6.6</version>
        </dependency>
    
        <dependency>
            <groupId>com.aliyun</groupId>
            <artifactId>aliyun-java-sdk-core</artifactId>
            <version>4.4.6</version>
        </dependency>
    </dependencies>



其他语言参考：[SDK列表](https://help.aliyun.com/document_detail/120968.html?spm=a2c4g.11186623.6.554.2c3c2151Q9GuJl)



* **Client初始化请参考** ：[安装新版Java SDK](https://help.aliyun.com/document_detail/120971.html?spm=a2c4g.11186623.6.555.32511cedAo8uQ7)

  



**注意**



**国内站RegionId固定使用为** **cn-hangzhou、国际站** **RegionId固定使用为** **ap-southeast-1。**

1.创建云解析付费实例 
--------------------------------

**描述** ：通过CreateInstance进行云解析付费实例创建。

**调用接口名称** ：CreateInstance

**接口参考文档** ：[实例创建服务 - 阿里云交易和账单管理API - 阿里云 (aliyun.com)](https://help.aliyun.com/document_detail/91835.html?spm=a2c4g.11186623.6.573.312469150RQ8t0)

**参数** **CreateInstanceRequest** **.** **Parameter说明：** 



![1 ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2997083161/p242166.png)


|-------------------|----------------------|------------------------------------------------------------------------|----------------------------|
| 接口参数              | Demo实例参数             | 取值范围                                                                   | 对应售卖页模块                    |
| Parameter.1.Code  | parameters1.setCode  | DNSSecurity                                                            | DNS安全                      |
| Parameter.1.Value | parameters1.setValue | no; basic; advenced                                                    | 不需要；DNS攻击基础防御；DNS攻击全力防御    |
| Parameter.2.Code  | parameters2.setCode  | DomainNumbers                                                          | 域名数量                       |
| Parameter.2.Value | parameters2.setValue | 1-100                                                                  | 域名数量的取值范围                  |
| Parameter.3.Code  | parameters3.setCode  | Version                                                                | 云解析版本选择                    |
| Parameter.3.Value | parameters3.setValue | version_personal；version_enterprise_basic； version_enterprise_advanced | 个人版 ；企业基础版；企业旗舰版           |
| Parameter.4.Code  | parameters4.setCode  | Domain                                                                 | 绑定域名名称                     |
| Parameter.4.Value | parameters4.setValue | example.com                                                            | 请输入实际绑定实例的域名，若多个域名，用英文逗号分隔 |



**常见问题** ：

（1）绑定域名信息的参数parameters4.setCode("Domain")，传值时首字母要 **大写** 。否则 **绑定域名失败** 。

（2）绑定的域名存在于购买实例的账号下，若为非万网域名，需要提前在云解析控制台进行域名添加，或者调用接口AddDomain进行添加。具体参考：[添加域名 - 云解析 DNS - 阿里云 (aliyun.com)](https://help.aliyun.com/document_detail/29749.html?spm=a2c4g.11174283.6.636.59e1571fGohpFX)

**调用Demo参考** ：

    package AlidnsTest.DomainManager;
    
    import com.alibaba.fastjson.JSON;
    import com.aliyuncs.bssopenapi.model.v20171214.CreateInstanceRequest;
    import com.aliyuncs.bssopenapi.model.v20171214.CreateInstanceResponse;
    import com.aliyuncs.exceptions.ClientException;
    import org.testng.annotations.Test;
    import org.testng.collections.Lists;
    import utils.AlidnsTestBase;
    
    public class InstanceCreateRenewUpgrade extends AlidnsTestBase {
    
        @Test
        public void createInstanceTest() {
            CreateInstanceRequest request = new CreateInstanceRequest();
            request.setProductCode("dns");
            request.setProductType("alidns_pre");
            request.setSubscriptionType("Subscription");
            request.setPeriod(1);
            CreateInstanceRequest.Parameter parameters1 = new CreateInstanceRequest.Parameter();
            parameters1.setCode("DNSSecurity");
            parameters1.setValue("no");
    
            CreateInstanceRequest.Parameter parameters2 = new CreateInstanceRequest.Parameter();
            parameters2.setCode("DomainNumbers");
            parameters2.setValue("1");
    
            CreateInstanceRequest.Parameter parameters3 = new CreateInstanceRequest.Parameter();
            parameters3.setCode("Version");
            parameters3.setValue("version_personal");
    
            CreateInstanceRequest.Parameter parameters4 = new CreateInstanceRequest.Parameter();
            parameters4.setCode("Domain");
            parameters4.setValue("example.taobao");
    
            request.setParameters(Lists.newArrayList(parameters1,parameters2,parameters3,parameters4));
            try {
                CreateInstanceResponse response = client.getAcsResponse(request);
                System.out.println(JSON.toJSON(response));
            } catch (ClientException e) {
                e.printStackTrace();
            }
        }
    }





2.云解析付费实例续费 
----------------------------------

**描述** ：通过RenewInstance进行云解析付费实例续费。

**调用接口名称** ：RenewInstance

**接口参考文档** ：[实例续费服务 - 阿里云交易和账单管理API - 阿里云 (aliyun.com)](https://help.aliyun.com/document_detail/91863.html?spm=a2c4g.11186623.6.576.39e22a1b0huzH8)

**调用Demo参考** ：

    package AlidnsTest.DomainManager;
    
    import com.alibaba.fastjson.JSON;
    import com.aliyuncs.bssopenapi.model.v20171214.CreateInstanceRequest;
    import com.aliyuncs.bssopenapi.model.v20171214.CreateInstanceResponse;
    import com.aliyuncs.bssopenapi.model.v20171214.RenewInstanceRequest;
    import com.aliyuncs.bssopenapi.model.v20171214.RenewInstanceResponse;
    import com.aliyuncs.exceptions.ClientException;
    import org.testng.annotations.Test;
    import org.testng.collections.Lists;
    import utils.AlidnsTestBase;
    
    public class OrderCreateRenewUpgrade extends AlidnsTestBase {
    
        /**
         * 云解析实例续费
         */
        @Test
        public void renewInstanceTest() {
            RenewInstanceRequest request = new RenewInstanceRequest();
            request.setInstanceId("dns-cn-oew21y7bh50"); // 填入真实创建的实例ID
            request.setProductCode("dns");
            request.setRenewPeriod(3);
            try {
                RenewInstanceResponse response = client.getAcsResponse(request);
                System.out.println(JSON.toJSON(response));
            } catch (ClientException e) {
                e.printStackTrace();
            }
        }
    }



3.云解析实例自动续费 
----------------------------------

**描述** ：通过SetRenewal设置云解析付费实例续费方式：手动续费、自动续费、不续费。

**调用接口名称** ：SetRenewal

**接口参考文档** ：[设置实例自动续费服务 - 阿里云交易和账单管理API - 阿里云 (aliyun.com)](https://help.aliyun.com/document_detail/91866.html?spm=a2c4g.11186623.6.577.5a5d6923OjmkQ0)

**自动续费周期参数说明** ：


|-------------------|----------------------------------------------------------------------|----------|
| 接口参数              | 取值范围                                                                 | 描述       |
| RenewalPeriodUnit | 取值：M：月。Y：年。                                                          | 自动续费周期单位 |
| RenewalPeriod     | RenewalPeriodUnit取值为年时，取值范围：1、2、3RenewalPeriodUnit取值为月时，取值范围：1、2、3、6 | 自动续费时长   |



**常见问题** ：

（1）ProductCode为必传参数

（2）当RenewalStatus= AutoRenewal时，RenewalPeriodUnit、RenewalPeriod为必传。

**调用Demo参考** ：

    package AlidnsTest.DomainManager;
    
    import com.alibaba.fastjson.JSON;
    import com.aliyuncs.bssopenapi.model.v20171214.*;
    import com.aliyuncs.exceptions.ClientException;
    import org.testng.annotations.Test;
    import org.testng.collections.Lists;
    import utils.AlidnsTestBase;
    
    public class OrderCreateRenewUpgrade extends AlidnsTestBase {
    
        /**
         * 云解析实例自动续费
         */
        @Test
        public void setRenewalTest() {
            SetRenewalRequest request = new SetRenewalRequest();
            request.setInstanceIDs("dns-cn-oew21y7bh50"); // 填入真实创建的实例ID
            request.setRenewalStatus("AutoRenewal");
            request.setProductCode("dns");
            request.setRenewalPeriodUnit("M");
            request.setRenewalPeriod(1);
            try {
                SetRenewalResponse response = client.getAcsResponse(request);
                System.out.println(JSON.toJSON(response));
            } catch (ClientException e){
                e.printStackTrace();
            }
        }
    }



4.云解析实例升级 
--------------------------------

**描述** ：通过ModifyInstance对云解析付费实例进行升级，目前云解析产品不支持付费实例降级。

**调用接口名称** ：ModifyInstance

**接口参考文档** ：[实例变更服务 - 阿里云交易和账单管理API - 阿里云 (aliyun.com)](https://help.aliyun.com/document_detail/91861.html?spm=a2c4g.11186623.6.575.7cfb6374po01XD)
**说明**

**Parameter.N.Code、** **Parameter.N.Value取值说明：** 

Parameter.N.Code传入Version即可。

Parameter.N.Value（云解析付费实例版本）取值范围：

* version_personal ： 个人版 ；

* version_enterprise_basic ： 企业基础版；

* version_enterprise_advanced： 企业旗舰版；




**常见问题** ：

（1）云解析付费实例目前不支持降级

（2） **InstanceId、** **ProductType** **为必传参数** 

调用Demo参考：

    package AlidnsTest.DomainManager;
    
    import com.alibaba.fastjson.JSON;
    import com.aliyuncs.bssopenapi.model.v20171214.*;
    import com.aliyuncs.exceptions.ClientException;
    import org.testng.annotations.Test;
    import org.testng.collections.Lists;
    import utils.AlidnsTestBase;
    
    public class OrderCreateRenewUpgrade extends AlidnsTestBase {
    
        /**
         * 云解析实例升级
         */
        @Test
        public void modifyInstanceTest() {
            ModifyInstanceRequest request = new ModifyInstanceRequest();
            request.setModifyType("Upgrade");
            ModifyInstanceRequest.Parameter parameters = new ModifyInstanceRequest.Parameter();
            parameters.setCode("Version");
            parameters.setValue("version_enterprise_basic");
            request.setParameters(Lists.newArrayList(parameters));
            request.setProductCode("dns");
            request.setProductType("alidns_pre");
            request.setSubscriptionType("Subscription");
            request.setInstanceId("dns-cn-oew21y7bh50"); // 填入真实创建的实例ID
            try {
                ModifyInstanceResponse response = client.getAcsResponse(request);
                System.out.println(JSON.toJSON(response));
            } catch (ClientException e) {
                e.printStackTrace();
            }
        }
    }



5.获取付费版DNS产品实例详情 
---------------------------------------

通过[](https://help.aliyun.com/document_detail/145538.html?spm=a2c4g.11186623.6.661.17f964e30eLr31)[获取付费版DNS产品实例详情](https://help.aliyun.com/document_detail/145538.html?spm=a2c4g.11186623.6.661.17f964e30eLr31)根据实例ID获取上述开通云解析收费版本产品实例的详情信息。

**调用Demo参考** ：

    package AlidnsTest.DomainManager;
    
    import com.alibaba.fastjson.JSON;
    import com.aliyuncs.alidns.model.v20150109.DescribeDnsProductInstanceRequest;
    import com.aliyuncs.alidns.model.v20150109.DescribeDnsProductInstanceResponse;
    import com.aliyuncs.bssopenapi.model.v20171214.*;
    import com.aliyuncs.exceptions.ClientException;
    import org.testng.annotations.Test;
    import org.testng.collections.Lists;
    import utils.AlidnsTestBase;
    
    public class OrderCreateRenewUpgrade extends AlidnsTestBase {
    
        /**
         * 获取云解析付费版实例详情
         */
    
        @Test
        public void describeDnsProductInstanceTest() {
            DescribeDnsProductInstanceRequest request = new DescribeDnsProductInstanceRequest();
            request.setInstanceId("dns-cn-oew21y7bh50"); // 填入真实创建的实例ID
            try {
                DescribeDnsProductInstanceResponse response = client.getAcsResponse(request);
                System.out.println(JSON.toJSON(response));
            } catch (ClientException e) {
                e.printStackTrace();
            }
        }
    }


