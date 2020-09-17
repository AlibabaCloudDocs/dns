Alibaba Cloud line for intelligent DNS resolution (September 16, 2020) 
===========================================================================================



Overview 
-----------------------------

Alibaba Cloud DNS supports location-based intelligent DNS resolution. This feature allows Alibaba Cloud DNS to return appropriate IP addresses to visitors based on the location of each visitor. When visitors at different locations access the same domain name, they are redirected to different IP addresses. This accelerates DNS resolution and reduces latency for access across networks or regions.

New line for intelligent DNS resolution 
------------------------------------------------------------

Beginning from September 16, 2020, Alibaba Cloud DNS Enterprise Standard Edition and Enterprise Ultimate Edition allow you to select the new Alibaba Cloud line when you configure intelligent DNS resolution for a domain name. This way, Alibaba Cloud DNS can return appropriate IP addresses to visitors based on the region where each visitor is located. The following table describes the new Alibaba Cloud line that is supported for intelligent DNS resolution.


|                                                                                                                    Line                                                                                                                    |         Subline         |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|
|              Alibaba Cloud | China (Qingdao)         |
|              Alibaba Cloud | China (Beijing)         |
|              Alibaba Cloud | China (Zhangjiakou)     |
|              Alibaba Cloud | China (Hohhot)          |
|              Alibaba Cloud | China (Hangzhou)        |
|              Alibaba Cloud | China (Shanghai)        |
|              Alibaba Cloud | China (Ulanqab)         |
|              Alibaba Cloud | China (Shenzhen)        |
|              Alibaba Cloud | China (Heyuan)          |
|              Alibaba Cloud | China (Guangzhou)       |
|              Alibaba Cloud | China (Chengdu)         |
|              Alibaba Cloud | China (Hong Kong)       |
|              Alibaba Cloud | Singapore               |
|              Alibaba Cloud | Australia (Sydney)      |
|              Alibaba Cloud | Malaysia (Kuala Lumpur) |
|              Alibaba Cloud | Indonesia (Jakarta)     |
|              Alibaba Cloud | Japan (Tokyo)           |
|              Alibaba Cloud | Germany (Frankfurt)     |
|              Alibaba Cloud | UK (London)             |
|              Alibaba Cloud | US (Silicon Valley)     |
|              Alibaba Cloud | US (Virginia)           |
|              Alibaba Cloud | India (Mumbai)          |
|              Alibaba Cloud | UAE (Dubai)             |



Scenario 
-----------------------------

You can select the Alibaba Cloud line when you configure intelligent DNS resolution for a domain name to **return appropriate IP addresses to visitors from different Alibaba Cloud regions** . This reduces resolution latency and improves user experience.

Sample configuration

The domain name www.dns-example.com is backed by three servers, whose IP addresses are 1.1.1.1, 2.2.2.2, and 3.3.3.3, respectively.

* A record is added to point the domain name to 1.1.1.1 by using the China (Hangzhou) line.

  

* A record is added to point the domain name to 2.2.2.2 by using the China (Beijing) line.

  

* A record is added to point the domain name to 3.3.3.3 by using the Singapore line.

  






Effect

* The IP address 1.1.1.1 is returned to visitors from the China (Hangzhou) region.

  

* The IP address 2.2.2.2 is returned to visitors from the China (Beijing) region.

  

* The IP address 3.3.3.3 is returned to visitors from the Singapore region.

  



