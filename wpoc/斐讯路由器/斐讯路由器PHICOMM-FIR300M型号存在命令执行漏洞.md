# 斐讯路由器PHICOMM-FIR300M型号存在命令执行漏洞

# 一、漏洞简介
斐讯路由器PHICOMM-FIR300M使用默认密码admin/admin登录后台后，系统管理的控制台功能虽然在前端过滤了敏感字符，但是在后端未对输入内容做校验，导致可抓包修改参数造成任意命令执行。

# 二、影响版本
+ 斐讯路由器PHICOMM-FIR300M

# 三、资产测绘
+ hunter`web.title=="FIR300M"`
+ 特征

![1699457151559-09e05449-f72f-444e-ab18-1178bd684415.png](./img/MQdwvYp3bC36b_KW/1699457151559-09e05449-f72f-444e-ab18-1178bd684415-100943.png)

# 四、漏洞复现
1.使用默认密码`admin/admin`登录路由器

![1699457195498-1b5878db-d293-4f80-a29c-99b09d3f2026.png](./img/MQdwvYp3bC36b_KW/1699457195498-1b5878db-d293-4f80-a29c-99b09d3f2026-944268.png)

2. `系统工具`->`系统诊断`

![1699457245475-e8944ca0-334f-4962-8ba4-091d17e18af1.png](./img/MQdwvYp3bC36b_KW/1699457245475-e8944ca0-334f-4962-8ba4-091d17e18af1-928663.png)

3. 修改ip地址为`8.8.8.8`，使用burp抓包,修改`pingAddr`参数为`ip|ls`后放行

![1699457354699-61ddc345-a148-4ab5-ab04-3677a181f8a9.png](./img/MQdwvYp3bC36b_KW/1699457354699-61ddc345-a148-4ab5-ab04-3677a181f8a9-455575.png)

![1699457718292-c9b1e951-6beb-42e1-b9bc-b5f630631da3.png](./img/MQdwvYp3bC36b_KW/1699457718292-c9b1e951-6beb-42e1-b9bc-b5f630631da3-598437.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lgwam74g3eagpt5z>