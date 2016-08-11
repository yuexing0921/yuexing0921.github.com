---
title: MongoDB 备份-归档命令
date: 2016-08-09 21:21:27
categories:
- MongoDB
tags:
- MongoDB
---
#### 备份-归档

方法一。无压缩内容

```
mongodump -h dympxxx.com --archive=test.20160705.archive --db test
mongorestore -h restroexxx.com, --archive=test.20160705.archive
```

方法二。压缩方式

```
mongodump -h dympxxx.com --gzip --archive=test.20160705.gz --db test
mongorestore -h restroexxx.com --gzip --archive=test.20160705.gz
```


也可以一行命令搞定

```
mongodump -h dympxxx.com --archive --db test --port 27017 | mongorestore  -h restroexxx.com  --archive --port 27018
```


###### 官方文档：

> mongodump
https://docs.mongodb.com/manual/reference/program/mongodump/
mongorestore
https://docs.mongodb.com/manual/reference/program/mongorestore/