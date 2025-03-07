# NetMizer 日志管理系统登录绕过漏洞

### 一、漏洞描述
NetMizer 日志管理系统存在登录绕过漏洞，通过限制某个请求包的发送获取后台权限

### 二、影响版本
<font style="color:#000000;">NetMizer</font>

### 三、资产测绘
```plain
title="NetMizer 日志管理系统"
```

![1720677624454-6b76b40a-5923-426e-9d81-63dd9d76617b.png](./img/PwoyZhBf6v8Nrgv0/1720677624454-6b76b40a-5923-426e-9d81-63dd9d76617b-032975.png)

### 四、漏洞复现
访问页面 main.html 并抓取请求包

```plain
/main.html
```

, Drop掉下面对请求包

![1720678035409-58d4a71b-02b3-455b-a0f1-df42bac53387.png](./img/PwoyZhBf6v8Nrgv0/1720678035409-58d4a71b-02b3-455b-a0f1-df42bac53387-098409.png)

直接进入后台

![1720678013546-1e4e9e3c-d746-4cba-b47f-757b6426e65a.png](./img/PwoyZhBf6v8Nrgv0/1720678013546-1e4e9e3c-d746-4cba-b47f-757b6426e65a-723156.png)



> 更新: 2024-08-12 17:48:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hgzz1oo7add2wvv4>