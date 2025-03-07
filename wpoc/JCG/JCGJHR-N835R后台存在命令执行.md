# JCG JHR-N835R 后台存在命令执行

# 一、漏洞简介
JCG JHR-N835R 后台存在命令执行，通过 ; 分割 ping 命令导致任意命令执行

# 二、影响版本
+ JCG JHR-N835R 

# 三、资产测绘
+ hunter`web.body="graphics/bottom.gif"`
+ 特征

![1700219199879-d6f8889d-692c-41ca-9223-e9669ff7cded.png](./img/P60bqolSQuyX5ldF/1700219199879-d6f8889d-692c-41ca-9223-e9669ff7cded-411046.png)

# 四、漏洞复现
1. 通过默认账号`admin/admin`登录

![1700219286833-d1c58fec-c420-48dd-ad6a-b35fdc0b3acd.png](./img/P60bqolSQuyX5ldF/1700219286833-d1c58fec-c420-48dd-ad6a-b35fdc0b3acd-436378.png)

2. 在后台系统工具那使用 PING工具，使用 ; 命令执行绕过

![1700219376026-a9ecdf59-448c-4f65-a04c-0c74b905c7cd.png](./img/P60bqolSQuyX5ldF/1700219376026-a9ecdf59-448c-4f65-a04c-0c74b905c7cd-505558.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xq0kmca04hi8g2yd>