---
title: 红米 AX6 路由器和群晖 NAS 单网口旁路由设置
author: 炒土豆丝
type: post
date: 2020-12-16T11:23:18+00:00
url: /nas-openwrt/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 4660
views:
  - 2250
categories:
  - it
tags:
  - 路由器

---
因为拼多多打骨折入手了红米 AX6 路由器，终于要用上 WIFI6 路由器了。然而问题来了，红米 AX6 没有第三方固件，没法在路由器上部署翻墙和过滤广告，很不方便。<figure class="wp-block-image size-large lightbox">

<img decoding="async" src="https://wp-archive.baka.li/2020/12/AX6-and-K3.jpg" alt="" /> <figcaption>红米 AX6 和它的前任斐讯 K3</figcaption> 

那怎么办？要翻墙，要低成本，要低功耗，还要稳定。

  * 方案1：K3 当主路由，AX6 当AP

有些浪费，功耗高，需要设置定时重启，有时候会断网需要重新连接 WAN 口和LAN 口才行，不知道为啥。

  * 方案2：升级 NAS 

升级到有双网口的 DS720+ 或者 DS920+ ，直接用群晖的虚拟机套件安装 OpenWrt 当做主路由，外接红米 AX6 当做 AP 。

缺点是成本过高，旧的 DS218+ 二手价格跌倒 1600 不到，出手就是血亏。

  * 方案3：X86 软路由

J1900 的软路由加上配件都得 500+ ，成本高功耗高对于已有 NAS 的我来说过于浪费。

  * 方案4：R2S 软路由

近期很火的 ARM 软路由，有官方的 OpenWrt 固件，也有 Lean 的，可玩性不错。而且功耗低，价格也只要 199 元。

因为 R2S 要等到月底才能发货，于是我尝试了下用 NAS 做旁路由，发现效果还不错，以上方案就 PASS 了。

下面简单介绍下怎么搞虚拟机软路由。

先看下网络拓扑图，光猫改桥接模式，使用主路由红米 AX6 进行拨号、DHCP分发，旁路由只负责翻墙。

<img decoding="async" src="https://wp-archive.baka.li/2020/12/my-home-network.png" alt="" class="wp-image-5854" />  

安装方法参考这篇文章：

<a href="https://blog.skk.moe/post/nas-dsm-vmm-lede/" target="_blank" rel="noreferrer noopener">单网口群晖使用 Virtual Machine Manager 安装 Koolshare OpenWRT 作为旁路网关</a>

不同的是我使用的固件是 eSir 编译的 <a href="https://drive.google.com/drive/folders/1eyIxVfyzO4nyzaT1sSr6xWf50_5YJN7g" target="_blank" rel="noreferrer noopener">OpenWrt 精品小包固件</a>，还有个高大全版，因为只用到了翻墙插件还是选个小巧的吧。Koolshare 是必源固件，个人不推荐安装。

主路由红米 AX6 的 IP 是 10.0.0.1 ，不需要做其他设置。

虚拟机旁路由 IP 是 10.0.0.10 ， LAN 口的设置如下：

<img loading="lazy" decoding="async" width="597" height="471" src="https://wp-archive.baka.li/2020/12/Openwrt-Settings-1.png" alt="" class="wp-image-5824" srcset="https://wp-archive.baka.li/2020/12/Openwrt-Settings-1.png 597w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-1-300x237.png 300w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-1-150x118.png 150w" sizes="(max-width: 597px) 100vw, 597px" />  

基本设置里给“忽略此接口”打勾，因为要用主路由提供 DHCP 服务。

<img loading="lazy" decoding="async" width="609" height="207" src="https://wp-archive.baka.li/2020/12/Openwrt-Settings-2.png" alt="" class="wp-image-5825" srcset="https://wp-archive.baka.li/2020/12/Openwrt-Settings-2.png 609w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-2-300x102.png 300w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-2-150x51.png 150w" sizes="(max-width: 609px) 100vw, 609px" />  

LAN 口的物理设置里的“桥接接口”还要去掉勾，点击保存。

<img loading="lazy" decoding="async" width="635" height="290" src="https://wp-archive.baka.li/2020/12/Openwrt-Settings-3.png" alt="" class="wp-image-5826" srcset="https://wp-archive.baka.li/2020/12/Openwrt-Settings-3.png 635w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-3-300x137.png 300w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-3-150x69.png 150w" sizes="(max-width: 635px) 100vw, 635px" />  

再在防火墙的自定义规则里添加一段规则，然后重启防火墙和应用设置。

<pre class="wp-block-code"><code>iptables -t nat -I POSTROUTING -j MASQUERADE</code></pre><figure class="wp-block-image size-large lightbox">

<img loading="lazy" decoding="async" width="933" height="568" src="https://wp-archive.baka.li/2020/12/Openwrt-Settings-4.png" alt="" class="wp-image-5827" srcset="https://wp-archive.baka.li/2020/12/Openwrt-Settings-4.png 933w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-4-300x183.png 300w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-4-150x91.png 150w, https://wp-archive.baka.li/2020/12/Openwrt-Settings-4-768x468.png 768w" sizes="(max-width: 933px) 100vw, 933px" />  

因为 AX6 的固件不能给设备下发网关和 DNS ，在需要翻墙的设备上需要手动设置网关和 DNS 。如在 iOS 系统的 IP 设置里，路由器指的就是网关，填旁路由的 IP ，DNS 也填旁路由的 IP 。

<img loading="lazy" decoding="async" width="406" height="480" src="https://wp-archive.baka.li/2020/12/ios-gateway.jpg" alt="" class="wp-image-5829" srcset="https://wp-archive.baka.li/2020/12/ios-gateway.jpg 406w, https://wp-archive.baka.li/2020/12/ios-gateway-254x300.jpg 254w, https://wp-archive.baka.li/2020/12/ios-gateway-127x150.jpg 127w" sizes="(max-width: 406px) 100vw, 406px" />  <img loading="lazy" decoding="async" width="480" height="436" src="https://wp-archive.baka.li/2020/12/ios-dns-1.jpg" alt="" class="wp-image-5858" /> 

Windows 设置：

<img loading="lazy" decoding="async" width="465" height="581" src="https://wp-archive.baka.li/2020/12/windows-gateway-1.png" alt="" class="wp-image-5860" />  

没有 NAS 的朋友还是建议买个 R2S 之类的软路由，比 N1 做旁路由更好折腾。