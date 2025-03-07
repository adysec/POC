# NetMizer 日志管理系统存在目录遍历漏洞

### 一、漏洞描述
北京灵州网络技术有限公司NetMizer日志管理系统存在目录遍历漏洞，由于 /data 控制不严格，攻击者可利用该漏洞获取敏感信息。

### 二、影响版本
<font style="color:#000000;">NetMizer</font>

### 三、资产测绘
```plain
title="NetMizer 日志管理系统"
```

![1720677624454-6b76b40a-5923-426e-9d81-63dd9d76617b.png](./img/zxlV67svFt2h_jMb/1720677624454-6b76b40a-5923-426e-9d81-63dd9d76617b-684031.png)

### 四、漏洞复现
```plain
/data/
```

![1720677771307-280e5029-0775-4c52-8e1a-8693bac733c3.png](./img/zxlV67svFt2h_jMb/1720677771307-280e5029-0775-4c52-8e1a-8693bac733c3-722431.png)



> 更新: 2024-08-12 17:48:54  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hqxda6dxd5064rpt>