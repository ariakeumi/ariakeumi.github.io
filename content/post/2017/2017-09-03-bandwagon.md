---
title: 2017，从 BudgetVM 搬家到搬瓦工
author: 炒土豆丝
type: post
date: 2017-09-03T14:16:11+00:00
url: /bandwagon/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 5805
dsq_thread_id:
  - 6117594425
views:
  - 733
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - it
tags:
  - VPS

---
 

2015年，我的博客从 5 美元一个月的 Digitalocean 搬到了&nbsp;BudgetVM ，因为 BudgetVM 最便宜的 512MB 内存 VPS 只要 25 美元一年。

BudgetVM 虽然很便宜，配置也还行，但是连接速度很慢，而且丢包严重。然后最近看到说搬瓦工（Bandwagon）推出了 [CN2 线路][1]&nbsp;的 VPS ，据说搭建 VPN 看 YouTube 4K 视频不卡，价格只要 30 美元一年，既能提高博客访问速度，还能顺便搭建 Shadowsocks ，VPS 到期后就迁移过去了。

<pre class="wp-block-preformatted">SPECIAL 10G KVM PROMO V3 - LOS ANGELES - CN2 
SSD: 10 GB RAID-10
RAM: 512 MB
CPU: 1x Intel Xeon
Transfer: 500 GB/mo
Link speed: 1 Gigabit</pre>

## [订购链接(支持支付宝)][2] 

[<img loading="lazy" decoding="async" width="1029" height="529" src="https://wp-archive.baka.li/2017/09/bandwagon-offer.png" alt="" class="wp-image-4886" srcset="https://wp-archive.baka.li/2017/09/bandwagon-offer.png 1029w, https://wp-archive.baka.li/2017/09/bandwagon-offer-150x77.png 150w, https://wp-archive.baka.li/2017/09/bandwagon-offer-300x154.png 300w, https://wp-archive.baka.li/2017/09/bandwagon-offer-768x395.png 768w, https://wp-archive.baka.li/2017/09/bandwagon-offer-1024x526.png 1024w" sizes="(max-width: 1029px) 100vw, 1029px" />][3] 

WordPress 迁移过程很方便，没遇到什么麻烦。用&nbsp;BackWPup 把 WordPress 目录和数据库备份到 Dropbox ，配置好 Lnmp ，直接在新 VPS 里面下载解压，导入数据库，提权 WordPress 目录就 OK 了。

搬瓦工这个 CN2 线路的 VPS 速度真的很给力，Ping 稳定在 160~170ms ，看 Twitch 六十帧原画毫无压力，强烈推荐。

 [1]: https://baike.baidu.com/item/CN2
 [2]: https://bwh1.net/cart.php?a=confproduct&i=0
 [3]: https://wp-archive.baka.li/2017/09/bandwagon-offer.png