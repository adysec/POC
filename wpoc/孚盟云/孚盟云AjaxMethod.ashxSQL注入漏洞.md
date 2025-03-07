# 孚盟云AjaxMethod.ashx SQL注入漏洞

# 一、漏洞简介
孚盟与阿里强强联手将最受青睐的经典C系列产品打造成全新的孚盟云产品，让用户可以用云模式实现信息化管理，让用户的异地办公更加流畅，大大降低中小企业在信息化上成本，用最小的投入享受大型企业级别的信息化服务，使中小企业在网络硬件环境、内部贸易过程管理与快速通关形成一套完整解决方案。

# 二、影响版本
+ 孚盟云CRM

# 三、资产测绘
+ hunter`app.name="孚盟云 CRM"`
+ 登录页面

![1693927610010-b856fdb9-d5da-4a65-b0c3-197c665b1d44.png](./img/3TX-gi-rq43CrYKh/1693927610010-b856fdb9-d5da-4a65-b0c3-197c665b1d44-038131.png)

# 四、漏洞复现
```plain
/Ajax/AjaxMethod.ashx?action=getEmpByname&Name=1
```

![1693927659635-ea1af5b1-5f90-4a5f-b9d9-98420438bc7e.png](./img/3TX-gi-rq43CrYKh/1693927659635-ea1af5b1-5f90-4a5f-b9d9-98420438bc7e-610567.png)

![1693928003514-3c2d3a36-6df6-45a5-972e-13703a75416f.png](./img/3TX-gi-rq43CrYKh/1693928003514-3c2d3a36-6df6-45a5-972e-13703a75416f-294343.png)



> 更新: 2024-02-29 23:55:47  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xubb5blcky307d56>