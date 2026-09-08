---
title: Shadowsocks 自动代理的应用
author: 炒土豆丝
type: post
date: 2014-12-04T01:40:33+00:00
url: /shadowsocks/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 4388
dsq_thread_id:
  - 3975479456
views:
  - 937
categories:
  - app
tags:
  - Android APP
  - IOS软件
  - Windows 软件

---
> Shadowsocks是一个轻量级socks5代理，以python写成；
> 
> 通过客户端以指定的密码、加密方式和端口连接服务器，成功连接到服务器后，客户端在用户的电脑上构建一个本地socks5代理。使用时将流量分到本地socks5代理，客户端将自动加密并转发流量到服务器，服务器以同样的加密方式将流量回传给客户端，以此实现代理上网。

<a class="ds-user-name ds-highlight" href="http://t.qq.com/noip117isend" target="_blank">茄子泥焗黄鱼</a>共享了一个 Shadowsocks 的账号给我，然后听说 Shadowsocks 可以在iOS上实现自动切换线路。

因为经常用到Google等海外网站和同步服务，如果每次用都要开VPN的话麻烦死了，在Android下只要root了就能很简单实现这些。

配置iOS的 Shadowsocks  比想象的简单的多&#8230;只要需要在Cydia商店下载 Shadowsocks ，然后填上账号密码端口再打勾自动代理就好了，这应该是目前iOS上最好的翻墙方案了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3315" src="https://wp-archive.baka.li/2014/12/Shadowsocks-ios.png" alt="Shadowsocks-ios" width="1680" height="1260" srcset="https://wp-archive.baka.li/2014/12/Shadowsocks-ios.png 1680w, https://wp-archive.baka.li/2014/12/Shadowsocks-ios-150x112.png 150w, https://wp-archive.baka.li/2014/12/Shadowsocks-ios-300x225.png 300w, https://wp-archive.baka.li/2014/12/Shadowsocks-ios-1024x768.png 1024w" sizes="(max-width: 1680px) 100vw, 1680px" />][1]

在 Android 下也差不多，可以到Play商店下载 <a href="https://play.google.com/store/apps/details?id=com.github.shadowsocks" target="_blank">Shadowsocks</a> ，好像root都不用。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3316" src="https://wp-archive.baka.li/2014/12/Shadowsocks-android.png" alt="Shadowsocks-android" width="432" height="720" srcset="https://wp-archive.baka.li/2014/12/Shadowsocks-android.png 768w, https://wp-archive.baka.li/2014/12/Shadowsocks-android-90x150.png 90w, https://wp-archive.baka.li/2014/12/Shadowsocks-android-180x300.png 180w, https://wp-archive.baka.li/2014/12/Shadowsocks-android-614x1024.png 614w" sizes="(max-width: 432px) 100vw, 432px" />][2]

在 Windows 下需要配合浏览器扩展才能实现自动代理。

下载 <a href="http://sourceforge.net/projects/shadowsocksgui/files/dist/shadowsocks-gui-0.6.4-win-ia32.tar.xz/download" target="_blank">Shadowsocks Windows GUI版</a>，直接填上账号密码端口然后保存就好了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3313" src="https://wp-archive.baka.li/2014/12/shadowsocks-gui.png" alt="shadowsocks-gui" width="362" height="452" srcset="https://wp-archive.baka.li/2014/12/shadowsocks-gui.png 362w, https://wp-archive.baka.li/2014/12/shadowsocks-gui-120x150.png 120w, https://wp-archive.baka.li/2014/12/shadowsocks-gui-240x300.png 240w" sizes="(max-width: 362px) 100vw, 362px" />][3]

然后到Chrome商店下载 <a href="https://chrome.google.com/webstore/detail/proxy-switchyomega/padekgcemlokbadohgkifijomclgjgif" target="_blank">SwitchyOmega</a> 这个扩展程序，设置好代理协议为SOCKS5，代理端口自行选择，再把自动切换规则弄好就行了。

和以前的GoAgent +  <a href="https://chrome.google.com/webstore/detail/dpplabbmogkhghncfbfdeeokoefdjegm" target="_blank">Proxy SwitchySharp</a> 弄起来一模一样，Shadowsocks + Proxy SwitchySharp 也行，但是自动切换会失效，全局还是可用，不知为何。 <a class="lightbox" href="https://chrome.google.com/webstore/detail/proxy-switchyomega/padekgcemlokbadohgkifijomclgjgif" target="_blank"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-3314" src="https://wp-archive.baka.li/2014/12/Shadowsocks-switchy.png" alt="Shadowsocks-switchy" width="1170" height="551" srcset="https://wp-archive.baka.li/2014/12/Shadowsocks-switchy.png 1170w, https://wp-archive.baka.li/2014/12/Shadowsocks-switchy-150x70.png 150w, https://wp-archive.baka.li/2014/12/Shadowsocks-switchy-300x141.png 300w, https://wp-archive.baka.li/2014/12/Shadowsocks-switchy-1024x482.png 1024w" sizes="(max-width: 1170px) 100vw, 1170px" /></a>

还有OpenWRT的版本，刚好我的路由器是OpenWRT的，等技术好还可以继续折腾&#8230;

 [1]: https://wp-archive.baka.li/2014/12/Shadowsocks-ios.png
 [2]: https://wp-archive.baka.li/2014/12/Shadowsocks-android.png
 [3]: https://wp-archive.baka.li/2014/12/shadowsocks-gui.png