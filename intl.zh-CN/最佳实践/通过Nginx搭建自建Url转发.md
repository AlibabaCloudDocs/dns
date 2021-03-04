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

url.aliyun.com为跳转前域名，www.aliyun.com为跳转后域名（配置时请更换为实际业务域名）

**场景一：将url.aliyun.com完全转发到www.aliyun.com** 

例如，访问http://url.aliyun.com/a.txt 需要跳转到 http://www.aliyun.com/a.txt

配置过程：

1. 配置nginx.conf文件，文件在安装文件时填写的路径位置，即--prefix=填入的路径。

   

2. 修改server模块中的server_name和location /模块的内容：

   





**说明**

重定向目前分为301永久重定向，302临时重定向，若您网站不涉及搜索引擎技术，则选择302临时重定向即可。

配置前：

![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/236819/1614737208014-545c52bc-47e5-4fb9-b8f3-41f248a7776e.png)

配置后：

![2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4228374161/p245159.png)

配置内容参考：

    server {
        
        server_name url.aliyun.com; # url.aliyun.com改为跳转前的域名
    
        location / {
            return 302 http://www.aliyun.com$request_uri; # http://www.aliyun.com 改为跳转后域名
        }
    }



4. 重启Nginx服务

   




    cd /usr/local/nginx/sbin #实际操作时更换为安装时配置的路径
    ./nginx -s reload



5. 验证效果

   




    #在服务器上运行
    curl -v http://gogo.dns-example.com/a.txt



![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/236819/1614671989274-3b7e49fe-96ff-4c7d-a1fa-7f2b1853228e.png)



**场景二：将url.aliyun.com完全转发到www.aliyun.com/b/** 

例如，访问http://url.aliyun.com/a.txt 需要跳转到 http://www.aliyun.com/b/a.txt

具体配置步骤参考场景一，nginx.conf配置内容参考：

    server {
        
        server_name url.aliyun.com; # url.aliyun.com改为跳转前的域名
    
        location / {
            return 302 http://www.aliyun.com/b$request_uri; # http://www.aliyun.com 改为跳转后域名
        }
    }





**场景三：将url.aliyun.com/xxx.xxx完全转发到http://www.aliyun.com** 

例如，访问http://url.aliyun.com/xxx.xxx需要跳转到http://www.aliyun.com

具体配置步骤参考场景一，nginx.conf配置内容参考：

    server {
        
        server_name url.aliyun.com; # url.aliyun.com改为跳转前的域名
    
        location / {
            return 302 http://www.aliyun.com; # http://www.aliyun.com 改为跳转后域名
        }
    }


