---
title: 近期搬瓦工 Shadowsocks 端口被大规模封锁
author: 炒土豆丝
type: post
date: 2019-02-06T11:24:56+00:00
url: /gfw-shadowsocks/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 9417
views:
  - 1508
categories:
  - it
tags:
  - Shadowsocks

---
年三十晚上，我的两台搬瓦工 VPS 上的 Shadowsocks 服务突然无法连接。

登录 SSH 检查服务无异常，重启服务依旧无法连接，既然 SSH 能连接，那么应该不会是被墙了。

然后就去检查下端口，果然，SS 服务所用的端口是无法连接的。

我是用 <span style="font-size: 16px; color: #24292e; font-family: -apple-system,BlinkMacSystemFont,;">libev 版的 Shadowsocks</span> 一键安装脚本安装的 SS ，修改 /etc/shadowsocks/config.json 配置文件里面的端口再重启 Shadowsocks 服务就正常了。

<pre class="lang:default decode:true  ">/etc/init.d/shadowsocks restart</pre>

因为昨天一个朋友也被封了端口，NGA&nbsp;也看到 <a href="http://nga.178.com/read.php?tid=16336249" target="_blank" rel="noopener noreferrer">SS&nbsp;服务端口被封</a> 的帖子，应该是大规模的封锁。墙已经越来越高了，现在建议使用 V2Ray 作为代理工具。

<a href="https://lala.im/1588.html" target="_blank" rel="noopener noreferrer">V2Ray简易配置使用教程-荒岛</a>