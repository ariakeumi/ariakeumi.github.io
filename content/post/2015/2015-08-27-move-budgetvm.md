---
title: 滚到 BudgetVM
author: 炒土豆丝
type: post
date: 2015-08-27T11:42:45+00:00
url: /move-budgetvm/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 2071
dsq_thread_id:
  - 4071611419
views:
  - 763
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
Digitalocean 的 VPS 快到期了，5刀一个月有点心疼，毕竟博客没人访问，还是换个便宜点的 VPS 吧。

主要要求是 512MB 内存，10GB 以上硬盘，机房在西海岸，价格便宜。

早先看中&nbsp;<a href="https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0CB8QFjAAahUKEwjj9tTXk8nHAhWPH44KHcC5CoU&url=https%3A%2F%2Fcrissic.net%2F&ei=wvPeVeONCY-_uATA86qoCA&usg=AFQjCNE9Z-VBlE4b08UoGvk51S8KE7FmGA&sig2=gH4pYNzrIjzjlSiLJ5bZ5g" target="_blank" rel="noopener">Crissic</a>&nbsp;，3刀一个月，速度还可以，刚要买的时候发现没货了。

然后发现家更便宜的，512MB 内存、25GB SSD 的年付只要35刀，机房在洛杉矶。

[<img loading="lazy" decoding="async" width="1162" height="402" src="https://wp-archive.baka.li/2015/08/budgetvm-openvz-ssd.png" alt="budgetvm-openvz-ssd" class="wp-image-4583" srcset="https://wp-archive.baka.li/2015/08/budgetvm-openvz-ssd.png 1162w, https://wp-archive.baka.li/2015/08/budgetvm-openvz-ssd-150x52.png 150w, https://wp-archive.baka.li/2015/08/budgetvm-openvz-ssd-300x104.png 300w, https://wp-archive.baka.li/2015/08/budgetvm-openvz-ssd-1024x354.png 1024w" sizes="(max-width: 1162px) 100vw, 1162px" />][1] 

25GB SSD 换成 50GB HDD 的话还能便宜 10刀，年付只要25刀！还支持支付宝付款，换算成人民币163块。

[<img loading="lazy" decoding="async" width="785" height="285" src="https://wp-archive.baka.li/2015/08/budgetvm-openvz-alipay.png" alt="budgetvm-openvz-alipay" class="wp-image-4584" srcset="https://wp-archive.baka.li/2015/08/budgetvm-openvz-alipay.png 785w, https://wp-archive.baka.li/2015/08/budgetvm-openvz-alipay-150x54.png 150w, https://wp-archive.baka.li/2015/08/budgetvm-openvz-alipay-300x109.png 300w" sizes="(max-width: 785px) 100vw, 785px" />][2] 

买的时候是深夜，西海岸时间应该是网络高峰期，连接上 SSH 敲命令都卡出翔，500ms 延迟加上感人的丢包验证了一分钱一分货的道理，将就用吧。

小插曲：系统选择的64位的&nbsp;CentOS &nbsp;，<a href="http://lnmp.org/" target="_blank" rel="noopener">lnmp</a> 安装失败，6.0 和 7.0 都这样，不知道什么原因，换成 Debian 也一样，最后换成32位的系统就好了。

 [1]: https://wp-archive.baka.li/2015/08/budgetvm-openvz-ssd.png
 [2]: https://wp-archive.baka.li/2015/08/budgetvm-openvz-alipay.png