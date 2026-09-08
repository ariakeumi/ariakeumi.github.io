---
title: DigitalOcean VPS 安装 Shadowsocks
author: 炒土豆丝
type: post
date: 2015-06-04T11:29:30+00:00
url: /digitalocean-vps-shadowsocks/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 2923
dsq_thread_id:
  - 3975481167
views:
  - 760
categories:
  - it
tags:
  - Shadowsocks
  - VPS

---
前几天朋友共享的 Shadowsocks 账号挂了，貌似是提供商 Shadowcheap 跑路了。为了翻墙需求，他准备买台VPS，由我打理。

> 虚拟专用服务器（英语：Virtual private server，缩写为 VPS），是指通过虚拟化技术在独立服务器中运行的专用服务器。每个使用VPS技术的虚拟独立服务器拥有各自独立的公网IP地址、操作系统、硬盘空间、内存空间、CPU资源等，还可以进行安装程序、重启服务器等操作，与运行一台独立服务器完全相同。

VPS提供商方面，选择了口碑较好价格实惠的DigitalOcean，5美元一个月的套餐，512MB内存，20GB固态硬盘，1TB一个月流量，应该够用了。

linux方面我完全是菜鸟，开始连登录VPS都不会&#8230;

还好这方面的教程很多，安装 Shadowsocks 服务端也不算难。

## <a href="https://www.zxc.so/do-ssh-key.html" target="_blank">DigitalOcean的Droplet怎么添加SSH Key和使用SSH Key登录</a>

当前我使用的是SSH Key登录，用 PuTTY Key Generator 生成公钥和私钥，VPS添加公钥，登录的时候用私钥验证，不用输入密码，挺方便的。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3947" src="https://wp-archive.baka.li/2015/06/putty-host.png" alt="putty-host" width="452" height="437" srcset="https://wp-archive.baka.li/2015/06/putty-host.png 452w, https://wp-archive.baka.li/2015/06/putty-host-150x145.png 150w, https://wp-archive.baka.li/2015/06/putty-host-300x290.png 300w" sizes="(max-width: 452px) 100vw, 452px" />][1]

CPU好YY，系统一不小心安装了Ubuntu&#8230;本来想装Debian的，因为我的笔记本就是Debian。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3920" src="https://wp-archive.baka.li/2015/06/digitalocean-vps-1.png" alt="digitalocean-vps-1" width="661" height="482" srcset="https://wp-archive.baka.li/2015/06/digitalocean-vps-1.png 661w, https://wp-archive.baka.li/2015/06/digitalocean-vps-1-150x109.png 150w, https://wp-archive.baka.li/2015/06/digitalocean-vps-1-300x219.png 300w" sizes="(max-width: 661px) 100vw, 661px" />][2]

## Ubuntu 安装 Shadowsocks

不是Root用户的首先切换，然后分别运行下面三条命令：

<pre class="lang:default decode:true ">apt-get update
apt-get install python-pip python-m2crypto supervisor
pip install shadowsocks</pre>

接着配置 supervisor，运行：

<pre class="lang:default decode:true">vi /etc/supervisord.conf</pre>

进入vi编辑器，复制下文再退出并保存。

<pre class="lang:default decode:true">[program:shadowsocks]
command=ssserver -c /etc/shadowsocks.json
autorestart=true
user=nobody</pre>

启动 supervisor：

<pre class="lang:default decode:true ">service supervisor start</pre>

接下来配置 Shadowsocks，运行

<pre class="lang:default decode:true ">vi /etc/shadowsocks.json</pre>

进入 vi 编辑器，键入下文再退出并保存。

<pre class="lang:default decode:true ">{
    "server":"服务器IP",
    "server_port":8388,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"密码",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false,
    "workers": 1
}</pre>

最后运行：

<pre class="lang:default decode:true ">ssserver -c /etc/shadowsocks.json -d start</pre>

总体来说安装起来还是挺简单的，不需要什么linux知识，多搜索下就好了。

测速，在美国西海岸带宽好给力。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3943" src="https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed-2.png" alt="DigitalOcean-VPS-speed-2" width="661" height="482" srcset="https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed-2.png 661w, https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed-2-150x109.png 150w, https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed-2-300x219.png 300w" sizes="(max-width: 661px) 100vw, 661px" />][3]

广东电信，看Youtube 720P视频毫无压力。

[<img loading="lazy" decoding="async" class=" size-full wp-image-3944 alignleft" src="https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed.png" alt="DigitalOcean-VPS-speed" width="300" height="135" srcset="https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed.png 300w, https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed-150x68.png 150w" sizes="(max-width: 300px) 100vw, 300px" />][4]

&nbsp;

&nbsp;

&nbsp;

&nbsp;

最后，祝波多尔斯基生日快乐。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3949" src="https://wp-archive.baka.li/2015/06/1985-06-04.png" alt="1985-06-04" width="589" height="302" srcset="https://wp-archive.baka.li/2015/06/1985-06-04.png 589w, https://wp-archive.baka.li/2015/06/1985-06-04-150x77.png 150w, https://wp-archive.baka.li/2015/06/1985-06-04-300x154.png 300w" sizes="(max-width: 589px) 100vw, 589px" />][5]

 [1]: https://wp-archive.baka.li/2015/06/putty-host.png
 [2]: https://wp-archive.baka.li/2015/06/digitalocean-vps-1.png
 [3]: https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed-2.png
 [4]: https://wp-archive.baka.li/2015/06/DigitalOcean-VPS-speed.png
 [5]: https://wp-archive.baka.li/2015/06/1985-06-04.png