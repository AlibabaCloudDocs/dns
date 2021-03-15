Set weights 
================================





Overview 
-----------------------------

Alibaba Cloud DNS allows you to set weights for IP addresses when you configure multiple IP addresses for a host record on a Domain Name System (DNS) server. When Alibaba Cloud DNS responds to DNS requests, Alibaba Cloud DNS returns different DNS records based on the preset weights of IP addresses. This way, traffic is forwarded to different servers, and load balancing is achieved.

Prerequisites 
----------------------------------

DNS records of your domain name have the same type, host record, and line. The supported types are A, CNAME, and AAAA.

Limits 
---------------------------

Weight settings apply only to DNS records that have the same type, **host record** , and **line** . The supported types are A, CNAME, and AAAA. The following table describes these limits in detail.


|              Limit              |                                                                                                                      Supported                                                                                                                      |                          Not supported                           |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| Record type                     | A, CNAME, and AAAA                                                                                                                                                                                                                                  | Other types                                                      |
| Record status                   | **Enabled** records                                                                                                                                                                                                                                 | **Paused** records, **locked** records, and wildcard DNS records |
| Number of DNS records supported | The free edition supports weight settings for a maximum of 10 DNS records that have the same type, host record, and line. The paid edition supports weight settings for a maximum of 90 DNS records that have the same type, host record, and line. | N/A                                                              |
| Weight                          | The weight for a DNS record can be set to a value in the range of 0 to 100. The default weight ratio of three DNS records is 1:1:1. If the weight for a DNS record is set to 0, Alibaba Cloud DNS does not return the DNS record.                   | N/A                                                              |
| Line                            | You can set it to a default line or a specific line for A records. **Note**  The weights are independent of each other in different lines.                                                                          | Enabling or disabling load balancing across different lines      |



GUI element description 
--------------------------------------------

![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6853975161/p249724.png)


| No. |        GUI element         |                                                                             Description                                                                             |
|-----|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | Load Balancing Policy      | This column displays the load balancing policy applied by the current account. Load balancing policies include Return all addresses and Return addresses by weight. |
| 2   | Return all addresses       | This value indicates that the domain name is resolved to multiple IP addresses and access traffic is evenly forwarded to each IP address.                           |
| 3   | Return addresses by weight | This value indicates that the domain name is resolved to multiple IP addresses and access traffic is forwarded to the IP addresses by weight.                       |
| 4   | EnableWeight               | Enabling weight settings is a global operation. This operation takes effect for all lines of a subdomain.                                                           |
| 5   | DisableWeight              | Disabling weight settings is a global operation. This operation takes effect for all lines of a subdomain.                                                          |
| 6   | Set weight                 | You can use this feature to enable weight settings and set weights for one or specific resolution lines.                                                            |



Setting method 
-----------------------------------

1 . Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com/dns/).

2 . On the **Authority Domains** tab of the Manage DNS page, click a domain name to go to the DNS Settings page.

![22](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7853975161/p249721.png)

3 . In the left-side navigation pane of the DNS Settings page, click **Weighted Round Robin** . On the page that appears, click **EnableWeight** in the Actions column corresponding to the domain name. The default weight ratio of three DNS records is 1:1:1. If the default weight ratio is retained, Alibaba Cloud DNS returns IP addresses to DNS requests based on this ratio.
**Note**



Enabling weight settings is a global operation. This operation takes effect for all lines of a subdomain.

![2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7853975161/p249723.png)![2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7853975161/p249725.png)

4 . On the Weighted Round Robin tab of the Weighted Round Robin page, click **Set Weight** . After you set weights, Alibaba Cloud DNS returns IP addresses to DNS requests based on the preset weights.

![2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7853975161/p249726.png)
**Note**

You can also enable weight settings for a specific line. To achieve this, perform the following steps:

To enable weight settings for a specific line, you can perform the global operation or separately enable weight settings for the line. Example:

1. Find the subdomain for which the load balancing policy is set to Return all addresses and click Set Weight.

   ![2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7853975161/p249729.png)
   

2. Select the line for which you want to enable weight settings.

   **Note**

   If the load balancing policy is Return all addresses and Line Weight Switch is turned off, the weights cannot be modified.

   ![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7853975161/p249731.png)
   

3. Turn on Line Weight Switch and set the weights in the Weight column based on your business needs.

   ![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7853975161/p249732.png)
   




**Result: The default line returns IP addresses based on the weight ratio of 1:1:1 and other lines return all IP addresses.** 

Result 
---------------------------

* Result of disabling weight settings

  




Assume that you have three servers whose IP addresses are `1.1.1.1`, `2.2.2.2`, and `3.3.3.3`. The IP addresses of these servers map to one domain name. The following table describes the DNS records of the domain name.


| Record type | Host record |  Line   | Record value |
|-------------|-------------|---------|--------------|
| A           | www         | Default | 1.1.1.1      |
| A           | www         | Default | 2.2.2.2      |
| A           | www         | Default | 3.3.3.3      |



When an on-premises DNS accesses Alibaba Cloud DNS, **Alibaba Cloud DNS returns all the three DNS records to the on-premises DNS** . The on-premises DNS sends all the IP addresses to the browser of a website visitor and the browser randomly accesses one of the IP addresses.

The preceding method can reduce the workloads of an authoritative DNS server to some extent. However, the method cannot differentiate between the servers or reflect the current status of each server.

* Result of default weight settings

  




If the weight settings are enabled, the default weight ratio of three DNS records is 1:1:1. **Alibaba Cloud DNS polls three A records and returns three IP addresses in sequence in response to DNS requests** . Alibaba Cloud DNS returns the following DNS records:

    Alibaba Cloud DNS returns 1.1.1.1 in response to a DNS request from Region 1.
    Alibaba Cloud DNS returns 2.2.2.2 in response to a DNS request from Region 2.
    Alibaba Cloud DNS returns 3.3.3.3 in response to a DNS request from Region 3.
    Alibaba Cloud DNS returns 1.1.1.1 in response to a DNS request from Region 4.
    Alibaba Cloud DNS returns 2.2.2.2 in response to a DNS request from Region 5.
    Alibaba Cloud DNS returns 3.3.3.3 in response to a DNS request from Region 6.
    ...





* Result of specified weight settings

  After the weight settings are **enabled** , you can **set weights** . Alibaba Cloud DNS returns IP addresses to DNS requests based on the weights. This way, traffic is forwarded to different servers based on the weights. For example, if the weight ratio of the preceding three DNS records is set to 2:1:1, the following DNS records are returned:

  

      Alibaba Cloud DNS returns 1.1.1.1 in response to a DNS request from Region 1.
      Alibaba Cloud DNS returns 2.2.2.2 in response to a DNS request from Region 2.
      Alibaba Cloud DNS returns 3.3.3.3 in response to a DNS request from Region 3.
      Alibaba Cloud DNS returns 1.1.1.1 in response to a DNS request from Region 4.
      Alibaba Cloud DNS returns 1.1.1.1 in response to a DNS request from Region 5.
      Alibaba Cloud DNS returns 2.2.2.2 in response to a DNS request from Region 6.
      ...

  



**Note**



You may find that DNS records are not returned based on the weight settings during the test. This is a common occurrence. The cause is that weighted round-robin is a coarse-grained method to schedule traffic based on the weight of an IP address in a DNS record. Weighted round-robin is set to process requests from on-premises DNSs. However, on-premises DNSs request the authoritative DNS, which is Alibaba Cloud DNS, only once within the time to live (TTL) period.

For example, a domain name is accessed by users in both the China (Shanghai) and China (Beijing) regions. Assume that users in the China (Shanghai) region use on-premises DNS A and users in the China (Beijing) region use on-premises DNS B. When on-premises DNS A and on-premises DNS B initiate requests to Alibaba Cloud DNS, Alibaba Cloud DNS returns IP addresses based on the weight settings. However, all users who use the same on-premises DNS obtain the same IP address within the TTL period.



