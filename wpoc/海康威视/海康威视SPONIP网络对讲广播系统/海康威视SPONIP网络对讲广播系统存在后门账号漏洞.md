# 海康威视SPON IP网络对讲广播系统存在后门账号漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统存在后门账号漏洞。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/rr6KagZV-W624Z1G/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-592211.png)

# 四、漏洞复现
后门账号在代码中写死的

```java
后门账号：
administrator/800823
```

![1704871100509-de3f1070-d8a7-4e6d-a1c0-1b9219a4e64a.png](./img/rr6KagZV-W624Z1G/1704871100509-de3f1070-d8a7-4e6d-a1c0-1b9219a4e64a-580031.png)

![1704871179647-001e8c87-cbe9-4899-8f1a-ff82ee3a1bff.png](./img/rr6KagZV-W624Z1G/1704871179647-001e8c87-cbe9-4899-8f1a-ff82ee3a1bff-773611.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rimo5nnt3a0yraea>