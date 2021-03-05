通过Nginx搭建自建Url转发 
=====================================



概述 {#STamU}
-----------

本文主要介绍如果通过Nginx的转发功能来自行搭建URL转发服务器，实现域名转发功能。



配置前提 {#PIwiH}
-------------

1.本文使用工具为Nginx，且确认http_rewrite_module是开启的，一般默认为开启状态。

2.Nginx安装配置方法，安装包编译安装：

    #下载安装包
    wget http://nginx.org/download/nginx-1.18.0.tar.gz
    #解压
    tar -zxvf nginx-1.18.0.tar.gz
    cd nginx-1.18.0
    
    ./configure --prefix=/usr/local/nginx #配置时更换为实际希望安装路径即可
    make && make install
    
    #安装完后验证是否安装成功
    cd /usr/local/nginx/sbin
    ./nginx -t 
    #出现如下内容为安装成功
    nginx: the configuration file /usr/local/nginx//conf/nginx.conf syntax is ok
    nginx: configuration file /usr/local/nginx//conf/nginx.conf test is successful





使用场景 {#0fU7Q}
-------------

根据使用场景不同，分为以下三个使用场景：
**说明**

url.dns-example.com为跳转前域名，www.aliyun.com为跳转后域名（配置时请更换为实际业务域名）

**场景一：将** url.dns-example.com **完全转发到www.aliyun.com** 

例如，访问url：http://url.dns-example.com/a.txt 需要跳转到 http://www.aliyun.com/a.txt

配置过程：

1. 配置nginx.conf文件，文件在安装文件时填写的路径位置，即--prefix=填入的路径。

   

2. 修改server模块中的server_name和location /模块的内容：

   





**说明**

重定向目前分为301永久重定向，302临时重定向，若您网站不涉及搜索引擎技术，则选择302临时重定向即可。

配置前：

![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/236819/1614737208014-545c52bc-47e5-4fb9-b8f3-41f248a7776e.png)

配置后：

![22](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4409094161/p245667.png)

配置内容参考：

    server {
        
        server_name url.dns-example.com; # url.dns-example.com改为跳转前的域名
    
        location / {
            return 302 http://www.aliyun.com$request_uri; # http://www.aliyun.com 改为跳转后域名
        }
    }



3. 重启服务

    cd /usr/local/nginx/sbin #实际操作时更换为安装时配置的路径
    ./nginx -s reload



4. 解析配置

   Nginx服务配置完毕后，需要将跳转前的域名解析指向到Nginx所在服务器IP上。即需要在域名的DNS服务商处添加一条url.dns-example.com（配置时更换为实际跳转前域名）的A记录指向到47.94.166.148（配置时更换为实际Nginx所在服务器）。
   




* 以云解析为例，详细步骤参考[添加解析](https://help.aliyun.com/knowledge_detail/29725.html?spm=a2c4g.11186623.2.2.7bc845camu9UKi#h2-a-1)，大致步骤如下：

  * 登录[云解析DNS控制台](http://dns.console.aliyun.com/)

    
  

  
  <!-- -->

  * 前往域名解析-权威域名-点击需要配置解析的域名进入解析列表页面
    。

    
  

  
  <!-- -->

  * 点击添加解析，进行如下解析配置。

    
  

  




![333](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2259094161/p245697.png)5. 验证效果

    #在服务器上运行
    curl -v http://url.dns-example.com/a.txt



![33](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4409094161/p245668.png)



**场景二：将** **url.dns-example.com** **完全转发到www.aliyun.com/b/** 

例如，访问http://url.dns-example.com/a.txt 需要跳转到 http://www.aliyun.com/b/a.txt

具体配置步骤参考场景一，nginx.conf配置内容参考：

    server {
        
        server_name url.dns-example.com; # url.dns-example.com改为跳转前的域名
    
        location / {
            return 302 http://www.aliyun.com/b$request_uri; # http://www.aliyun.com 改为跳转后域名
        }
    }





**场景三：将** **url.dns-example.com** **/xxx.xxx完全转发到http://www.aliyun.com** 

例如，访问http://url.dns-example.com/xxx.xxx需要跳转到http://www.aliyun.com

具体配置步骤参考场景一，nginx.conf配置内容参考：

    server {
        
        server_name url.dns-example.com; # url.dns-example.com改为跳转前的域名
    
        location / {
            return 302 http://www.aliyun.com; # http://www.aliyun.com 改为跳转后域名
        }
    }


