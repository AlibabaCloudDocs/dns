Renewal and upgrade 
========================================





Manual renewal {#h2-u7EEDu8D391}
--------------------------------

**Procedure** 

1 . Log on to the [Alibaba Cloud DNS console.](https://dns.console.aliyun.com)

2 . On the Manage DNS page, click the **Version Packages** tab and then **Renew** in the Actions column.

![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6841975161/p249679.png)

Auto-renewal {#h2-u81EAu52A8u7EEDu8D39u8BBEu7F6E2}
--------------------------------------------------

1 . Log on to the [Alibaba Cloud DNS console.](https://dns.console.aliyun.com)

2 . On the Manage DNS page, click the **Version Packages** tab and then **Configure Auto Renew** .

3 . Find the ID of the instance for which you want to enable auto-renewal and click **Enable Auto-Renew** in the Actions column.

![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6841975161/p249682.png)![2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6841975161/p249685.png)![3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6841975161/p249686.png)

Upgrade {#h2-u5347u7EA73}
-------------------------

1 . Log on to the [Alibaba Cloud DNS console.](https://dns.console.aliyun.com)

2 . On the Manage DNS page, click the **Version Packages** tab and then **Upgrade** in the Actions column.

![2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6841975161/p249688.png)

Limits {#h2-u4EA7u54C1u9650u52364}
----------------------------------

**Renewal** 

You will be notified of renewal by emails or text messages before your subscription to an Alibaba Cloud DNS instance is due to expire. After the subscription expires, your Domain Name System (DNS) configuration will be retained for another seven days. If you do not renew the subscription after the subscription expires for seven days, the system automatically releases the Alibaba Cloud DNS instance. The system also moves your DNS records to a free Alibaba Cloud DNS cluster.
**Notice**



* If your domain name is provided by HiChina, DNS resolution is not interrupted when the DNS servers are switched from a paid cluster to the free cluster. If your domain name is in the serverUpdateProhibited or clientUpdateProhibited state, the security lock is enabled for your domain name. In this case, the automatic downgrade may fail and the website may be inaccessible. To resolve this issue, you must manually change the DNS server.

  

* If your domain name is not provided by HiChina, you must change the DNS server to a DNS server provided by the domain name registrar or a free DNS server of Alibaba Cloud.

  




**Auto-renewal** 

If you select **Auto-renewal** when you purchase an Alibaba Cloud DNS instance, the system will send you a notification and automatically generate a renewal order before your purchased instance expires. Manual renewal is not required. The auto-renewal period for an Alibaba Cloud DNS instance with a monthly subscription is one month. The auto-renewal period of an Alibaba Cloud DNS instance with a yearly subscription is one year. 

**Upgrade** 

Alibaba Cloud DNS can be upgraded to a higher edition but cannot be downgraded.
