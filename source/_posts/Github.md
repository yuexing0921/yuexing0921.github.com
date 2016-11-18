---
title: GitHub速度慢的解决方案
date: 2016-11-18 09:17:29
tags:
---
最近一段时间Github速度变的非常慢，从github下载只有2-8KB的速度，实在难以忍受。
猜测是DNS污染了，然后g了下，果然如此。
那怎么解决尼，直接在修改hosts，不经过DNS服务器，这样就快了。
把下面代码贴到你的hosts文件粘贴下就好了,下载速度变成30KB-40KB之间。
linux 
```bash
vi /etc/hosts
```
windows 记得用administrator（管理员）命令输入
```bash
notepad C:\Windows\System32\drivers\etc\hosts
```

```
# Github
151.101.88.249 github.global.ssl.fastly.net 
151.101.16.249 github.global.ssl.fastly.net 
151.101.76.249 github.global.ssl.fastly.net 
151.101.24.249 github.global.ssl.fastly.net 

151.101.16.133 assets-cdn.github.com documentcloud.github.com raw.github.com training.github.com
151.101.100.133 assets-cdn.github.com documentcloud.github.com raw.github.com training.github.com
151.101.24.133  assets-cdn.github.com documentcloud.github.com raw.github.com training.github.com
151.101.40.133 assets-cdn.github.com documentcloud.github.com raw.github.com training.github.com
192.30.253.112 github.com www.github.com
192.30.253.113  github.com www.github.com

192.30.253.120  nodeload.github.com
192.30.253.121  nodeload.github.com

50.19.102.235   status.github.com
174.129.238.225   status.github.com
50.16.250.205   status.github.com
23.21.89.183   status.github.com
```

---
- 授人以鱼不如授人以渔，如果上面的代码贴上，依然失效，那么就要查看是不是github IP地址是否变更了，
- 通过http://tool.chinaz.com/dns/ 这个网站，依次输入上面各个域名的IP，然后修改下IP地址就可以了。
- 如果依然失效，那么就必须要科学的上网了，VPN，用shadowsocks等等工具。