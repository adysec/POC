# 大华智能物联综合管理平台(ICC)存在逻辑漏洞

# 一、漏洞简介
浙江大华技术股份有限公司，是全球领先的以视频为核心的智慧物联解决方案提供商和运营服务商，大华智能物联综合管理平台(ICC)存在逻辑漏洞，可登陆应用后台。

# 二、影响版本
+ 大华智能物联综合管理平台(ICC)

# 三、资产测绘
+ hunter`web.body="*客户端会小于800*"`
+ 特征

![1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004.png](./img/7yaQI2AUPtTcYV-V/1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004-409869.png)

# 四、漏洞复现
api信息泄露

```java
/api
```

![1698336313178-f8761ff1-b3af-4327-bf1a-a7b0d9a06aa2.png](./img/7yaQI2AUPtTcYV-V/1698336313178-f8761ff1-b3af-4327-bf1a-a7b0d9a06aa2-537818.png)

任意密码登陆

<font style="color:rgb(51,51,51);">直接输入账户</font>`<font style="color:rgb(51,51,51);">justForTest</font>`<font style="color:rgb(51,51,51);">，密码任意输入,直接进入后台。界面如下</font>

![1698336392454-6bf25ac0-92a2-47c5-99a4-5dfaf5c4cd87.png](./img/7yaQI2AUPtTcYV-V/1698336392454-6bf25ac0-92a2-47c5-99a4-5dfaf5c4cd87-832347.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gos4ilum1dcbrzp3>