Purchase, renew, and upgrade an Alibaba Cloud DNS instance by calling API operations 
=========================================================================================================

This topic describes how to use API operations to purchase, renew, upgrade, and enable auto-renewal for an Alibaba Cloud DNS instance. Specific parameter values in the sample code are for reference only. In actual calls, specify values as needed for such parameters, for example, Domain and InstanceId.

SDK 
------------------------

* **Maven dependencies** :

  




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



For more information about SDKs in other languages, see [SDK list.](https://www.alibabacloud.com/help/zh/doc-detail/120968.htm)



* **For more information about client initialization, see** [Install the latest Java SDK.](https://www.alibabacloud.com/help/zh/doc-detail/120971.htm?spm=a2c63.p38356.b99.15.6a3a2389He0nUJ)

  



**Notice**



**If you are a user on the China site (aliyun.com), set the RegionId parameter to cn-hangzhou. If you are a user on the International site (alibabacloud.com), set the RegionId parameter to ap-southeast-1.**

1. Create a paid Alibaba Cloud DNS instance 
----------------------------------------------------------------

**Description** : You can call the CreateInstance operation to create a paid Alibaba Cloud DNS instance.

**Operation** : CreateInstance

**References** : [CreateInstance](https://www.alibabacloud.com/help/zh/doc-detail/91835.htm?spm=a2c63.p38356.b99.32.6babb559OSfsbi)

**Description of request parameters:** 

![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6615155161/p248922.png)


|-------------------|-----------------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| Parameter         | Sample parameter name | Valid value                                                                 | Corresponding module on the buy page                                                                            |
| Parameter.1.Code  | parameters1.setCode   | DNSSecurity                                                                 | DNS Protection                                                                                                  |
| Parameter.1.Value | parameters1.setValue  | no, basic, and advenced                                                     | Not Required, DNS Attack Defense Basic, and DNS Attack Defense Advanced                                         |
| Parameter.2.Code  | parameters2.setCode   | DomainNumbers                                                               | Quantity                                                                                                        |
| Parameter.2.Value | parameters2.setValue  | 1-100                                                                       | Specify the number of domain names.                                                                             |
| Parameter.3.Code  | parameters3.setCode   | Version                                                                     | Select Edition                                                                                                  |
| Parameter.3.Value | parameters3.setValue  | version_personal, version_enterprise_basic, and version_enterprise_advanced | Personal Edition, Enterprise Standard Edition, and Enterprise Ultimate Edition                                  |
| Parameter.4.Code  | parameters4.setCode   | Domain                                                                      | Enter Domain Name                                                                                               |
| Parameter.4.Value | parameters4.setValue  | example.com                                                                 | Specify one or more domain names that are bound to the instance. Separate multiple domain names with commas (,) |



**FAQ** :

(1) When you set the parameters4.setCode parameter, the first letter of the domain name must be **capitalized** . Otherwise, **the instance cannot be bound to the domain name** .

(2) The bound domain name must exist under the account that purchases the instance. If you want to bind a domain name that is not provided by HiChina, you must add the domain name in advance in the Alibaba Cloud DNS console or by calling the AddDomain operation. For more information, see [Adding a domain name.](https://www.alibabacloud.com/help/zh/doc-detail/29749.htm)

**Sample code** :

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





2. Renew a paid Alibaba Cloud DNS instance 
---------------------------------------------------------------

**Description** : You can call the RenewInstance operation to renew a paid Alibaba Cloud DNS instance.

**Operation** : RenewInstance

**References** : [RenewInstance.](https://www.alibabacloud.com/help/zh/doc-detail/91863.htm?spm=a2c63.p38356.b99.35.7d9ccf5foQcJ70)

**Sample code** :

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
         * Renew an Alibaba Cloud DNS instance.
         */
        @Test
        public void renewInstanceTest() {
            RenewInstanceRequest request = new RenewInstanceRequest();
            request.setInstanceId("dns-cn-oew21y7bh50"); // The ID of the created instance.
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



3. Enable auto-renewal for an Alibaba Cloud DNS instance 
-----------------------------------------------------------------------------

**Description** : You can call the SetRenewal operation to enable auto-renewal for a paid Alibaba Cloud DNS instance. The following renewal methods are supported: manual renewal, auto-renewal, and non-renewal.

**Operation** : SetRenewal

**References** : [SetRenewal.](https://www.alibabacloud.com/help/zh/doc-detail/91866.htm?spm=a2c63.p38356.b99.36.60746d09OtiN4I)

**The following table describes the parameters related to the auto-renewal period.** 


|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
| Parameter         | Valid value                                                                                                                                                                                                      | Description                          |
| RenewalPeriodUnit | M: month. Y: year.                                                                                                                                                                                               | The unit of the auto-renewal period. |
| RenewalPeriod     | If the RenewalPeriodUnit parameter is set to Y, you can set the RenewalPeriod parameter to 1, 2, or 3. If the RenewalPeriodUnit parameter is set to M, you can set the RenewalPeriod parameter to 1, 2, 3, or 6. | The auto-renewal period.             |



**FAQ** :

(1) The ProductCode parameter is required.

(2) If you set the RenewalStatus parameter to AutoRenewal, the RenewalPeriodUnit and RenewalPeriod parameters are required.

**Sample code** :

    package AlidnsTest.DomainManager;
    
    import com.alibaba.fastjson.JSON;
    import com.aliyuncs.bssopenapi.model.v20171214.*;
    import com.aliyuncs.exceptions.ClientException;
    import org.testng.annotations.Test;
    import org.testng.collections.Lists;
    import utils.AlidnsTestBase;
    
    public class OrderCreateRenewUpgrade extends AlidnsTestBase {
    
        /**
         * Enable auto-renewal for an Alibaba Cloud DNS instance.
         */
        @Test
        public void setRenewalTest() {
            SetRenewalRequest request = new SetRenewalRequest();
            request.setInstanceIDs("dns-cn-oew21y7bh50"); // The ID of the created instance.
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



4. Upgrade an Alibaba Cloud DNS instance 
-------------------------------------------------------------

**Description** : You can call the ModifyInstance operation to upgrade a paid Alibaba Cloud instance. Alibaba Cloud DNS does not support downgrading paid instances.

**Operation** : ModifyInstance

**References** : [ModifyInstance.](https://www.alibabacloud.com/help/zh/doc-detail/91861.htm?spm=a2c63.p38356.b99.34.299f2426srr8Eq)
**Note**

**Valid values of the Parameter.N.Code and Parameter.N.Value parameters:** 

Set the Parameter.N.Code parameter to Version.

You can set the Parameter.N.Value parameter for a paid Alibaba Cloud DNS instance to the following values:

* version_personal

  

* version_enterprise_basic

  

* version_enterprise_advanced

  




**FAQ** :

(1) Paid Alibaba Cloud DNS instances cannot be downgraded.

(2) The **InstanceId** and **ProductType** parameters are **required** .

Sample code:

    package AlidnsTest.DomainManager;
    
    import com.alibaba.fastjson.JSON;
    import com.aliyuncs.bssopenapi.model.v20171214.*;
    import com.aliyuncs.exceptions.ClientException;
    import org.testng.annotations.Test;
    import org.testng.collections.Lists;
    import utils.AlidnsTestBase;
    
    public class OrderCreateRenewUpgrade extends AlidnsTestBase {
    
        /**
         * Upgrade an Alibaba Cloud DNS instance.
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
            request.setInstanceId("dns-cn-oew21y7bh50"); // The ID of the created instance.
            try {
                ModifyInstanceResponse response = client.getAcsResponse(request);
                System.out.println(JSON.toJSON(response));
            } catch (ClientException e) {
                e.printStackTrace();
            }
        }
    }



5. Query the details about a paid Alibaba Cloud DNS instance 
---------------------------------------------------------------------------------

You can call the [DescribeDnsProductInstance](https://www.alibabacloud.com/help/zh/doc-detail/145538.htm?spm=a2c63.p38356.b99.85.683a408ejxv6aS) operation to query the details about the paid Alibaba Cloud DNS instance based on the instance ID.

**Sample code** :

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
         * Query the details about a paid Alibaba Cloud DNS instance.
         */
    
        @Test
        public void describeDnsProductInstanceTest() {
            DescribeDnsProductInstanceRequest request = new DescribeDnsProductInstanceRequest();
            request.setInstanceId("dns-cn-oew21y7bh50"); // The ID of the created instance.
            try {
                DescribeDnsProductInstanceResponse response = client.getAcsResponse(request);
                System.out.println(JSON.toJSON(response));
            } catch (ClientException e) {
                e.printStackTrace();
            }
        }
    }


