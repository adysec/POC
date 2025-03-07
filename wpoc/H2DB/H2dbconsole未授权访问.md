# H2db console 未授权访问

# 一、漏洞简介
H2 database是一款Java内存数据库，多用于单元测试。H2 database自带一个Web管理页面，在Spirng开发中，如果我们设置如下选项，即可允许外部用户访问Web管理页面，且没有鉴权：

spring.h2.console.enabled=true  
spring.h2.console.settings.web-allow-others=true  
利用这个管理页面，我们可以进行JNDI注入攻击，进而在目标环境下执行任意命令。

# 二、影响版本
+ H2db console 

# 三、资产测绘
+ hunter`web.title="H2 Console"`
+ 特征

![1698938977757-5a84b3ed-9af6-4a39-9192-0a640c403137.png](./img/Wn3sGvLw1T50-kc2/1698938977757-5a84b3ed-9af6-4a39-9192-0a640c403137-807420.png)

# 四、漏洞复现
点击连接直接登陆

![1698939747766-ce382cf1-fd30-4072-a243-d056254aa53c.png](./img/Wn3sGvLw1T50-kc2/1698939747766-ce382cf1-fd30-4072-a243-d056254aa53c-612815.png)

![1698939773633-8e03f70c-e23b-4740-8f8e-040bd0a3bafd.png](./img/Wn3sGvLw1T50-kc2/1698939773633-8e03f70c-e23b-4740-8f8e-040bd0a3bafd-654250.png)

可执行sql命令

![1698939824783-9a31e347-1b96-4a4c-ada7-f5f33758d27d.png](./img/Wn3sGvLw1T50-kc2/1698939824783-9a31e347-1b96-4a4c-ada7-f5f33758d27d-400521.png)  




> 更新: 2024-02-29 23:57:33  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tvx8qos5yau1kggz>