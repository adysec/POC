# Grafana存在未授权访问漏洞

# 一、漏洞描述
Grafana是一个开源的可视化和分析平台，一个通用的可视化工具。‘通用’意味着Grafana不仅仅适用于展示Prometheus下的监控数据，也同样适用于一些其他的数据可视化需求。Grafana存在未授权访问漏洞，未经身份验证的用户可以绕过前端安全认证，未授权访问通过登录页面访问系统仪表板区域。

# 二、影响版本
Grafana

# 三、资产测绘
```plain
app="Grafana"
```

![1727014008181-843b9798-1b88-4f7d-a968-ec49cfcfc74a.png](./img/Jh4jQ6Q82EoPxhu7/1727014008181-843b9798-1b88-4f7d-a968-ec49cfcfc74a-024790.png)

# 三、漏洞复现
```plain
/?orgId=1
```

![1727013899091-bb094584-ee26-41f8-b445-b706c96dd975.png](./img/Jh4jQ6Q82EoPxhu7/1727013899091-bb094584-ee26-41f8-b445-b706c96dd975-586462.png)

```plain
/metrics
```



> 更新: 2024-10-22 09:41:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/iwh76cslo7q2l2wy>