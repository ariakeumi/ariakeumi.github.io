---
title: 甲骨文 ARM 服务器安装 Debian + xfce 桌面
author: 炒土豆丝
type: post
date: 2023-04-17T12:31:00+00:00
url: /oracle-arm-debian-xfce/
image: https://wp-archive.baka.li/2023/04/oracle-arm-debian-xfce.webp
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 567
categories:
  - app
tags:
  - Linux
  - VPS

---
创建一个 4 核 24 GB 内存的 ARM 实例，系统选择 Ubuntu 20.04 。

SSH 连接到服务器，先用萌咖脚本 DD 个 Debian 11 系统。

<pre class="wp-block-code"><code>#更新apt源
apt-get update
#安装需要的工具包
apt-get install -y xz-utils openssl gawk file
#安装 Debian11
bash &lt;(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 11 -v 64 -a -firmware</code></pre>

等待几分钟 DD 安装完毕之后，请立即更新密码。默认用户名为：root，默认密码为：MoeClub.org 。

再次 SSH 连接服务器，安装 xfce 桌面以及 xrdp :

<pre class="wp-block-code"><code>apt-get update
apt install -y xfce4 dbus-x11 xrdp</code></pre>

修改 xrdp 端口 :

<pre class="wp-block-code"><code>#更换为高位端口
vi /etc/xrdp/xrdp.ini
prot = 3389 
#重启 xrdp 服务
service xrdp restart</code></pre>

使用 Microsoft 远程桌面连接到服务器。

<img loading="lazy" decoding="async" width="1348" height="792" src="https://wp-archive.baka.li/2023/04/oracle-arm-debian-xfce.png" alt="" class="wp-image-6370" />  

为什么要给服务器安装图形界面？

当然是为了安装浏览器然后给老司機論壇的账号挂机刷在线时间升级，方便以后发帖求车啊。

PS：Google Chrome 没有适配 ARM Linux 版，需要安装 Chromium ，并且在 VPS 上启动还需要加上 &#8211;no-sandbox 参数。