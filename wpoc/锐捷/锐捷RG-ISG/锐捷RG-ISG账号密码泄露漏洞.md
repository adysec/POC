# 锐捷RG-ISG账号密码泄露漏洞

**一、漏洞简介**

<font style="color:rgb(51, 51, 51);">锐捷ISG存在账号密码泄露漏洞，可以获取密码的md5值, 解密后获取后台权限</font>

**二、影响版本**  
锐捷RG-ISG  
**三、资产测绘**

`title="RG-ISG"`  
●登录页面

![1711904678558-9afdd3ad-2c1b-4252-bdef-cc1a79b99a05.png](./img/rsF9R9NFuIVrcSRD/1711904678558-9afdd3ad-2c1b-4252-bdef-cc1a79b99a05-504193.webp)

  
**四、漏洞复现**  


首页查看源代码，搜索<font style="color:rgb(0, 0, 0);">persons </font>字段

![1712097097492-45caba67-a4aa-4bec-997c-e67d7a85d510.png](./img/rsF9R9NFuIVrcSRD/1712097097492-45caba67-a4aa-4bec-997c-e67d7a85d510-994591.png)

![1712097137836-f93be1b8-8a0b-45a4-995c-75bade1d2434.png](./img/rsF9R9NFuIVrcSRD/1712097137836-f93be1b8-8a0b-45a4-995c-75bade1d2434-642070.png)

  




> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gq2226cz30ascc2d>