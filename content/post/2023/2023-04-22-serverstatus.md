---
title: 部署一个轻量高颜值的服务器监控探针 ServerStatus
author: 炒土豆丝
type: post
date: 2023-04-21T20:14:33+00:00
url: /serverstatus/
image: "https://wp-archive.baka.li/2023/04/serverstatus-card.png"
featured_image: https://wp-archive.baka.li/2023/04/serverstatus-card.png
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - 'false'
argon_show_post_outdated_info:
  - default
views:
  - 501
categories:
  - it
  - app
tags:
  - Linux
  - VPS

---
## 介绍 

<a href="https://blog.moe.lol/" target="_blank" rel="noreferrer noopener">cokemine</a>/<a href="https://github.com/cokemine/ServerStatus-Hotaru" target="_blank" rel="noreferrer noopener">ServerStatus-Hotaru</a> 是一个基于 PHP 和 Python 编写的服务器状态监控工具，可在 Web 界面上展示服务器的 CPU、内存、磁盘、网络等状态信息，还支持对服务器的进程、端口等信息进行监控。它可以实时更新服务器的状态信息，方便系统管理员进行监控和管理。

我稍微修改了下 <a href="https://github.com/cokemine/ServerStatus-Hotaru" target="_blank" rel="noreferrer noopener">ServerStatus-Hotaru</a> 的主题，去掉了原生主题的 Banner ，让卡片显示 CPU 型号和内存硬盘大小，如下图。

<img loading="lazy" decoding="async" width="1359" height="834" src="https://wp-archive.baka.li/2023/04/serverstatus-card.png" alt="" class="wp-image-6489" />  

## 安装服务端 

<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/cokemine/ServerStatus-Hotaru/master/status.sh
# wget https://cokemine.coding.net/p/hotarunet/d/ServerStatus-Hotaru/git/raw/master/status.sh 若服务器位于中国大陆建议选择 Coding.net 仓库
bash status.sh s</code></pre>

此安装脚本会安装 Caddy 来作为 Web 服务器，如果需要用 Nginx ，把 /usr/local/ServerStatus/web 目录设置为网站根目录。

## 配置 ServerStatus 

修改配置文件 /usr/local/ServerStatus/server/config.json ，填入你的服务器节点信息。

CPU 型号用 cat /proc/cpuinfo 来查看。region 用于显示卡片的国旗，国家代码参考 <a rel="noreferrer noopener" href="https://zh.wikipedia.org/wiki/ISO_3166-1%E4%BA%8C%E4%BD%8D%E5%AD%97%E6%AF%8D%E4%BB%A3%E7%A0%81#%E6%AD%A3%E5%BC%8F%E5%88%86%E9%85%8D%E4%BB%A3%E7%A0%81" target="_blank">ISO 3166-1 alpha-2</a> 。

<pre class="wp-block-code"><code>  {
   "username": "用户名",
   "password": "密码",
   "name": "节点名字",
   "type": "操作系统",
   "host": "处理器型号",
   "location": "服务器位置",
   "disabled": false,
   "region": "US"
  },</code></pre>

## 安装客户端 

  * **Linux 发行版**

<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/cokemine/ServerStatus-Hotaru/master/status.sh
# wget https://cokemine.coding.net/p/hotarunet/d/ServerStatus-Hotaru/git/raw/master/status.sh 若服务器位于中国大陆建议选择 Coding.net 仓库
bash status.sh c</code></pre>

  * **OpenWrt 路由器**

在这种设备中建议使用 Go 客户端，在 <a href="https://github.com/cokemine/ServerStatus-goclient/releases" target="_blank" rel="noreferrer noopener">ServerStatus-goclient/releases</a> 下载对应的二进制客户端并解压到 /root 目录，SSH 连接到路由器，执行下面的命令。

如果不需要监控 WAN 口流量可以不用安装 vnstat 。

<pre class="wp-block-code"><code>opkg update
opkg install nohup
opkg install vnstat
chmod +x status-client
nohup ./status-client -dsn="username:password@yourip:35601" -vnstat &</code></pre>

Go 客户端可能无法正确识别磁盘容量，如果有需求得安装 <a rel="noreferrer noopener" href="https://github.com/cokemine/ServerStatus-Hotaru/blob/master/clients/status-psutil.py" target="_blank">Python 客户端</a> ，安装完 Python 和依赖要占用几十兆空间，个人不建议。

  * **群晖 NAS**

在 <a rel="noreferrer noopener" href="https://github.com/cokemine/ServerStatus-goclient/releases" target="_blank">ServerStatus-goclient/releases</a> 下载对应的二进制客户端。

解压并上传到你的群晖 NAS 的任意目录。在群晖的控制面板设置，计划任务里新增 [ 触发的任务 ]， [ 用户定义的脚本 ] ，事件选择 [ 开机 ] ，运行命令填下面的这行，路径和用户名密码 IP 替换成自己的。

<pre class="wp-block-code"><code>/volume1/docker/serverstatus/status-client -dsn="username:password@yourip:35601"</code></pre>

再点操作栏的 运行 ，这样客户端就在后台运行并开机自启了。

<img loading="lazy" decoding="async" width="957" height="669" src="https://wp-archive.baka.li/2023/04/serverstatus-dsm.png" alt="" class="wp-image-6488" />  

  * **Windows**

在 <a rel="noreferrer noopener" href="https://github.com/cokemine/ServerStatus-goclient/releases" target="_blank">ServerStatus-goclient/releases</a> 下载对应的二进制客户端并解压到任意目录，通过 Powershell 运行以下命令后台运行，路径和用户名密码 IP 记得替换。

<pre class="wp-block-code"><code>Start-Process -FilePath "C:\Users\Umi\Desktop\status-client.exe" -ArgumentList '-dsn="username:password@yourip:35601"' -WindowStyle Hidden -Verb RunAs</code></pre>

如果需要开机自启动配置个 vbs 脚本并在计划任务里设置登录自动打开就行：

```
Set objShell = CreateObject("WScript.Shell")
objShell.Run """C:\Users\Documents\scrutiny\status-client.exe"" -dsn=""username:password@yourip:3560""", 0, False
```

## ServerStatus 主题修改版 

我的探针： <a rel="noreferrer noopener" href="https://s.umi.im/" target="_blank">ServerStatus</a> ，在 Onedrive 下载 <a rel="noreferrer noopener" href="https://1drv.ms/u/s!Agj1VU8aYuuBgfJPM4_mwUhKn0oq7w?e=nurKaE" target="_blank">我的主题</a> ，替换掉 /usr/local/ServerStatus/web 目录。

<img loading="lazy" decoding="async" width="1916" height="1185" src="https://wp-archive.baka.li/2023/04/ServerStatus.webp" alt="" class="wp-image-6467" srcset="https://wp-archive.baka.li/2023/04/ServerStatus.webp 1916w, https://wp-archive.baka.li/2023/04/ServerStatus-1536x950.webp 1536w" sizes="(max-width: 1916px) 100vw, 1916px" /> 