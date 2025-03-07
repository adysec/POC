# Redis存在未授权访问导致的RCE

# 一、漏洞描述
redis是一个非常快速的，开源的，支持网络，可以基于内存，也可以持久化的日志型，非关系型的键值对数据库。并提供了多种语言的api。有java，c/c++,c#,php，JavaScript，perl，object-c，python，ruby，erlang等客户端，使用方便。Redis存在未授权访问导致的RCE

# 二、影响版本
Redis

# 三、资产测绘
```plain
app="redis"
```

![1730008100396-b60c7ec9-97aa-491a-9229-cc41975bfbaa.png](./img/1fBdiLYyi01ByAzn/1730008100396-b60c7ec9-97aa-491a-9229-cc41975bfbaa-952279.png)

# 三、漏洞复现
![1730008135522-2752b193-04f5-44d4-87cc-e50cbe4683ac.png](./img/1fBdiLYyi01ByAzn/1730008135522-2752b193-04f5-44d4-87cc-e50cbe4683ac-462694.png)

反弹shell使用脚本

[RedisGetshell.py](https://www.yuque.com/attachments/yuque/0/2024/txt/29512878/1732673083520-cd32abee-9703-4958-aa1c-02c3d6e94e7b.txt)

```plain
python RedisGetshell.py -H 127.0.0.1 -P 6379
```

选3，之后输入自己vps地址，即可反弹shell

![1730008351143-c3229d9a-105e-4908-be63-0acbd96e26d4.png](./img/1fBdiLYyi01ByAzn/1730008351143-c3229d9a-105e-4908-be63-0acbd96e26d4-139525.png)

![1730008405363-cfa5d390-7a75-4ebd-b35d-8b44b0307856.png](./img/1fBdiLYyi01ByAzn/1730008405363-cfa5d390-7a75-4ebd-b35d-8b44b0307856-287531.png)



> 更新: 2024-11-27 10:04:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hrg8q2mccg664x20>