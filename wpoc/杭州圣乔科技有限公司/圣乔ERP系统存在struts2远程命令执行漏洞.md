# 圣乔ERP系统存在struts2远程命令执行漏洞

# 一、漏洞简介
杭州圣乔科技有限公司成立于2007年02月27日，注册地位于浙江省杭州市拱墅区和睦路555号201幢116室，法定代表人为张鹏。经营范围包括计算机软硬件、电子产品的技术开发、销售。圣乔ERP系统存在struts2远程命令执行漏洞

# 二、影响版本
+ 圣乔ERP系统

# 三、资产测绘
+ hunter`web.icon="d2c808114296ddd9e76e9c774d79bd43"`
+ fofa`app="圣乔-ERP系统"`
+ 特征

![1730869080978-12b99405-c009-4ad9-859b-18e58e139dc8.png](./img/iQrJOGDYU3xmx0IV/1730869080978-12b99405-c009-4ad9-859b-18e58e139dc8-963827.png)

# 四、漏洞复现
```java
/shengfeng/login.action
```

![1730869093319-2c1db21f-5781-4e14-a1a5-03075a51a6ee.png](./img/iQrJOGDYU3xmx0IV/1730869093319-2c1db21f-5781-4e14-a1a5-03075a51a6ee-323929.png)

```plain
/erp/login.action
```

![1730905698826-0bcf624e-28b5-4c23-ba75-3bd4e21a4cdd.png](./img/iQrJOGDYU3xmx0IV/1730905698826-0bcf624e-28b5-4c23-ba75-3bd4e21a4cdd-226170.png)



> 更新: 2024-11-27 10:00:07  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ht9nkwf0kxowxnhw>