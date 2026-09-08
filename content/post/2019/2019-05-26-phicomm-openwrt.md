---
title: 斐讯 K2 K2P K3 OpenWRT 固件存档
author: 炒土豆丝
type: post
date: 2019-05-25T20:19:32+00:00
url: /phicomm-openwrt/
wpb_post_views_count:
  - 11238
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
views:
  - 1633
categories:
  - app
tags:
  - 路由器

---
 



近期，多位路由器固件开发者被约谈喝茶，并被迫删除了包含固件下载链接的帖子，因为他们的路由器固件里面包含了能翻墙的组件。

受影响的包括斐讯路由器官改固件开发者 abccba94 ，OpenWRT 固件开发者 Lean ，老毛子固件（Padavan）开发者荒野无灯 和 hanwckf 等大神。

<img loading="lazy" decoding="async" width="777" height="419" src="https://wp-archive.baka.li/2019/05/right-lean.jpg" alt="" class="wp-image-5536" srcset="https://wp-archive.baka.li/2019/05/right-lean.jpg 777w, https://wp-archive.baka.li/2019/05/right-lean-150x81.jpg 150w, https://wp-archive.baka.li/2019/05/right-lean-300x162.jpg 300w, https://wp-archive.baka.li/2019/05/right-lean-768x414.jpg 768w" sizes="(max-width: 777px) 100vw, 777px" />  <img loading="lazy" decoding="async" width="851" height="384" src="https://wp-archive.baka.li/2019/05/right-abc.jpg" alt="" class="wp-image-5546" srcset="https://wp-archive.baka.li/2019/05/right-abc.jpg 851w, https://wp-archive.baka.li/2019/05/right-abc-150x68.jpg 150w, https://wp-archive.baka.li/2019/05/right-abc-300x135.jpg 300w, https://wp-archive.baka.li/2019/05/right-abc-768x347.jpg 768w" sizes="(max-width: 851px) 100vw, 851px" /> <img loading="lazy" decoding="async" width="614" height="126" src="https://wp-archive.baka.li/2019/05/p4davan.png" alt="" class="wp-image-5544" srcset="https://wp-archive.baka.li/2019/05/p4davan.png 614w, https://wp-archive.baka.li/2019/05/p4davan-150x31.png 150w, https://wp-archive.baka.li/2019/05/p4davan-300x62.png 300w" sizes="(max-width: 614px) 100vw, 614px" /> 

本文主要是备份下我所用的路由器的固件，都是以 Lean 的 OpenWRT 固件源码开发的。

  * 斐讯 K2 PSG1218 A版 （OpenWRT）
  * 斐讯 K2P A1 / A2 MTK版 （PandoraBox 和官改固件）
  * 斐讯 K3 （OpenWRT）

OpenWRT 因为其强大的功能，可定制性和 Material Design 主题成为我最喜欢的路由器固件，PandoraBox 也是其分支，设置基本都一样。

[<img loading="lazy" decoding="async" width="1161" height="769" src="https://wp-archive.baka.li/2019/05/Image-041.png" alt="" class="wp-image-5532" srcset="https://wp-archive.baka.li/2019/05/Image-041.png 1161w, https://wp-archive.baka.li/2019/05/Image-041-150x99.png 150w, https://wp-archive.baka.li/2019/05/Image-041-300x199.png 300w, https://wp-archive.baka.li/2019/05/Image-041-768x509.png 768w, https://wp-archive.baka.li/2019/05/Image-041-1024x678.png 1024w" sizes="(max-width: 1161px) 100vw, 1161px" />][1] 

Lean 的固件里面的翻墙组件 Shadowsocks Plus + 是隐藏的，登录 SSH 输入以下命令回车即可开启。

<pre class="wp-block-code"><code>echo 0xDEADBEEF &gt; /etc/config/google_fu_mode</code></pre>

K2 和 K2P 都是在 Breed 里面刷入固件的，随便刷。

K3 可以直接在官改固件里刷 LEDE 过渡固件，再刷 Lean 的 OpenWRT ，lede-bcm53xx-phicomm-k3-squashfs-factory-20170504.bin 这个是过渡固件。

至于 K2 / K2P 怎么刷入 Breed 或者 K3 怎么刷官改固件，恩山上还有很多教程，应该没删。

下载链接：

<https://pan.baidu.com/s/17Ab0uW7R6PxsydfTLAHa4g> 提取码: xepj 

<https://drive.google.com/drive/folders/1IuyyrFJz4GjI7bI7QQS5nZ9-YQe754IV?usp=sharing>

 [1]: https://wp-archive.baka.li/2019/05/Image-041.png