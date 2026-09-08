---
title: 通过 Home Assistant 让 OpenWrt 软路由的 CPU 温度显示在苹果 Homekit 上
author: 炒土豆丝
type: post
date: 2021-04-08T01:23:46+00:00
url: /homekit-openwrt-cpu-temperature/
wpb_post_views_count:
  - 2073
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
views:
  - 1845
categories:
  - app
tags:
  - Apple

---
通过 Home Assistant 的 Synology 集成我们已经可以让群晖的CPU温度显示在 Homekit 上，我使用的 NanoPi R2S 路由器 CPU 发热很严重，为了方便查看路由器温度决定尝试下看看能不能接入 Home Assistant。

Home Assistant 官方有 OpenWrt 集成，可惜那个只能追踪设备。搜了下确实有成功把路由器温度接入 Home Assistant 的案例，一个是 K3 官改固件一个是梅林固件，并没有 OpenWrt 的。

<a href="https://bbs.hassbian.com/thread-9376-1-1.html" target="_blank" rel="noreferrer noopener">[技术探讨] 监测K3路由器温度</a>

<a href="https://bbs.hassbian.com/thread-3517-1-1.html" target="_blank" rel="noreferrer noopener">[进阶教程] 梅林路由器CPU和无线芯片温度接入Home Assistant</a>

我参考第一个链接通过 Command Line 成功让软路由的温度显示在 Home Assistant 和 Homekit 上。<figure class="wp-block-image size-large is-resized">

<img loading="lazy" decoding="async" src="https://wp-archive.baka.li/2021/04/homekit-r2s-temperature.jpg" alt="" class="wp-image-5890" width="395" height="640" />  

方法如下：

  1. 打开 Home Assistant 的终端，以我通过群晖 Docker 安装的 Home Assistant 为例，打开 Docker 应用的容器选项，找到 Home Assistant 的容器，点上面的详情，再切换终端机，新建 bash，进入终端界面了。
  2. 输入 ssh-keygen 回车创建密钥，输入密钥的名字，然后回提示你设置密码，密码留空直接回车两下就创建完成了。

我这里的私钥 id\_rsa （图上名字填错）和公钥 id\_rsa.pub 都存在 /config 目录下。

<pre class="wp-block-code"><code>ssh-keygen</code></pre><figure class="wp-block-image size-large is-resized">

<img loading="lazy" decoding="async" src="https://wp-archive.baka.li/2021/04/Home-Assistant-Bash.jpg" alt="" class="wp-image-5888" width="850" height="545" />  

3. 输入 cat id_rsa.pub 回车查看公钥，拷贝里面的内容。

<pre class="wp-block-code"><code>cat id_rsa.pub</code></pre>

在 OpenWrt 界面的 系统 &#8211; 管理权 &#8211; SSH密钥 中粘贴并应用。

<img loading="lazy" decoding="async" width="926" height="603" src="https://wp-archive.baka.li/2021/04/OpenWrt-RSA.png" alt="" class="wp-image-5889" />  

4. 在 Home Assistant 的终端输入下面的命令测试，成功会输出温度数字。如果失败，尝试赋予 id_rsa 私钥文件 700 权限。

<pre class="wp-block-code"><code>chmod -R 700 id_rsa
ssh -o StrictHostKeyChecking=no -i /config/id_rsa root@路由器IP cut -c1-2 /sys/class/thermal/thermal_zone0/temp</code></pre>

5. 在 Home Assistant 的 configuration.yaml 配置文件添加下面的配置并重启 Home Assistant 服务，就能在 Home Assistant 和 Homekit 里看到路由器温度的传感器了。

<pre class="wp-block-code"><code>homekit:

sensor:
  - platform: command_line
    name: R2S CPU 温度
    command: "ssh -o StrictHostKeyChecking=no -i /config/id_rsa root@路由器IP cut -c1-2 /sys/class/thermal/thermal_zone0/temp"
    unit_of_measurement: "°C"
    scan_interval: 300</code></pre>