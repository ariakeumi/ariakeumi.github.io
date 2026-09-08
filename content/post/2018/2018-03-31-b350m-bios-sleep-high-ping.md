---
title: 微星 B350M 主板 BIOS 导致 Windows 系统从睡眠唤醒后网络延迟变高而且游戏卡顿
author: 炒土豆丝
type: post
date: 2018-03-30T20:55:23+00:00
url: /b350m-bios-sleep-high-ping/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 3585
views:
  - 1002
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
enclosure:
  - |
    |
        https://wp-archive.baka.li/2018/04/overwatch-bad-ping.mp4
        1332561
        video/mp4
        
categories:
  - it

---
 

三月中旬的时候，电脑开始出现了一个极其怪异的现象。

在使用&nbsp;Windows&nbsp;的睡眠（Sleep）再唤醒电脑玩守望先锋时，游戏延迟会很高，而且感觉丢包很严重，走路走两步都会顿一下（网络卡那种），基本上玩不下去了。

这种现象只有在系统从睡眠中唤醒后才会出现，重启电脑再玩就没问题了。可是我用了 Win10&nbsp;后就养成了不关机只睡眠的习惯，因为睡眠可以保留内存信息，唤醒后可以回到睡眠前的内存状态。

睡眠前：

[<img loading="lazy" decoding="async" width="397" height="62" src="https://wp-archive.baka.li/2018/04/overwatch-ping-1.png" alt="" class="wp-image-5169" srcset="https://wp-archive.baka.li/2018/04/overwatch-ping-1.png 397w, https://wp-archive.baka.li/2018/04/overwatch-ping-1-150x23.png 150w, https://wp-archive.baka.li/2018/04/overwatch-ping-1-300x47.png 300w" sizes="(max-width: 397px) 100vw, 397px" />][1] [<img loading="lazy" decoding="async" width="916" height="512" src="https://wp-archive.baka.li/2018/03/ping-qq-baidu-1.png" alt="" class="wp-image-5178" srcset="https://wp-archive.baka.li/2018/03/ping-qq-baidu-1.png 916w, https://wp-archive.baka.li/2018/03/ping-qq-baidu-1-150x84.png 150w, https://wp-archive.baka.li/2018/03/ping-qq-baidu-1-300x168.png 300w, https://wp-archive.baka.li/2018/03/ping-qq-baidu-1-768x429.png 768w" sizes="(max-width: 916px) 100vw, 916px" />][2] 

睡眠唤醒后：

[<img loading="lazy" decoding="async" width="396" height="62" src="https://wp-archive.baka.li/2018/04/overwatch-ping-2.png" alt="" class="wp-image-5170" srcset="https://wp-archive.baka.li/2018/04/overwatch-ping-2.png 396w, https://wp-archive.baka.li/2018/04/overwatch-ping-2-150x23.png 150w, https://wp-archive.baka.li/2018/04/overwatch-ping-2-300x47.png 300w" sizes="(max-width: 396px) 100vw, 396px" />][3] [<img loading="lazy" decoding="async" width="916" height="512" src="https://wp-archive.baka.li/2018/03/ping-qq-baidu-2.png" alt="" class="wp-image-5179" srcset="https://wp-archive.baka.li/2018/03/ping-qq-baidu-2.png 916w, https://wp-archive.baka.li/2018/03/ping-qq-baidu-2-150x84.png 150w, https://wp-archive.baka.li/2018/03/ping-qq-baidu-2-300x168.png 300w, https://wp-archive.baka.li/2018/03/ping-qq-baidu-2-768x429.png 768w" sizes="(max-width: 916px) 100vw, 916px" />][4] 

以上是我网络很稳定的时候测试，确实是系统睡眠唤醒后会延迟增加，延迟本身高那么唤醒后增加的幅度更高。

更为奇怪的是，虽然延迟只提高一点，但是游戏里却比爆 Ping&nbsp;的时候卡多了。

比如下面这个视频里，里面的滑梯是一顿一顿的闪过来，很夸张。<figure class="wp-block-video"><video controls src="https://wp-archive.baka.li/2018/04/overwatch-bad-ping.mp4"></video> 

经过了半个月的慢慢排除&#8230;

  * 路由器导致的问题？

在第一次出现这个现象后，我就重启了路由器，但是延迟依旧高。

因为那段时间给我的斐讯 K3&nbsp;路由器刷了固件并部署了 Shadowsocks ，所以重点怀疑对象就是路由器。

经过各种修改设置，直至重置了路由器，问题依旧。

最后使用光猫并在电脑上拨号，睡眠唤醒后的高延迟还在，至此排除了路由器的问题。

  * 光猫发神经？

因为没有备用的光猫，没法用排除法，但是重启光猫也是那样，如果是光猫的问题重启系统就能解决也太玄乎了吧。

  * 软件的锅？

排查了任务管理器，资源监视器的各种进程，清理了注册表，卸载了一堆软件，还是不行。

  * 系统 BUG？

Windows 10&nbsp;教育版 1709&nbsp;版本，升级到了 1803 （创意者更新春季版）没有解决。

最后，新建一个分区，再安装一个&nbsp;Windows 10 ，还是唤醒后延迟变高。

  * 硬件GG了？

似乎相关的硬件也就网卡了，要么就坏了没法用，不太可能会互相这种奇怪的问题，回滚了网卡驱动也不行。

  * 罪魁祸首居然是它！

再排除掉路由器、驱动软件、系统的问题后，决定死马当活马医，先重置下 BIOS 。

结果，居然解决了？那到底具体是哪里的问题呢？

再多次调试 BIOS&nbsp;再反复确认后，排除了内存超频，WOL&nbsp;唤醒等设置，终于找到了问题的根源。

是 CPU&nbsp;超频导致的问题，把 CPU&nbsp;频率和电压调回默认就好了。

[<img loading="lazy" decoding="async" width="1024" height="768" src="https://wp-archive.baka.li/2018/04/b350m-bios-cpu-oc.jpg" alt="" class="wp-image-5172" srcset="https://wp-archive.baka.li/2018/04/b350m-bios-cpu-oc.jpg 1024w, https://wp-archive.baka.li/2018/04/b350m-bios-cpu-oc-150x113.jpg 150w, https://wp-archive.baka.li/2018/04/b350m-bios-cpu-oc-300x225.jpg 300w, https://wp-archive.baka.li/2018/04/b350m-bios-cpu-oc-768x576.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" />][5] 

但是我的 CPU&nbsp;长期都是超频使用的，以前也没出现这个问题。

去 B350M&nbsp;MORTAR&nbsp;的产品支持页面看到 BIOS&nbsp;的更新日期后才回想起来。

发布日期为 2018&nbsp;年 3 月 12 日，版本号为&nbsp;7A37v1B&nbsp;的主板 BIOS&nbsp;我刚好在三月更新了，这版本 BIOS&nbsp;提高了内存兼容性，让我的芝奇幻光戟能稳定在 2993MHz&nbsp;运行，同时也让我出现了 CPU&nbsp;超频导致&nbsp;Windows&nbsp;睡眠唤醒后延迟变高的诡异问题。

[<img loading="lazy" decoding="async" width="527" height="223" src="https://wp-archive.baka.li/2018/04/B350M-BIOS-2018-03.png" alt="" class="wp-image-5163" srcset="https://wp-archive.baka.li/2018/04/B350M-BIOS-2018-03.png 527w, https://wp-archive.baka.li/2018/04/B350M-BIOS-2018-03-150x63.png 150w, https://wp-archive.baka.li/2018/04/B350M-BIOS-2018-03-300x127.png 300w" sizes="(max-width: 527px) 100vw, 527px" />][6] 

在更新 7A37v1E&nbsp;版本的 BIOS&nbsp;后，问题终于解决了。

划重点：微星（MSI）B350M MORTAR&nbsp;主板&nbsp;7A37v1B&nbsp;版本的 BIOS&nbsp;固件在 CPU&nbsp;超频后会导致&nbsp;Windows&nbsp;系统从睡眠中唤醒后网络延迟变高，游戏卡顿。

 [1]: https://wp-archive.baka.li/2018/04/overwatch-ping-1.png
 [2]: https://wp-archive.baka.li/2018/03/ping-qq-baidu-1.png
 [3]: https://wp-archive.baka.li/2018/04/overwatch-ping-2.png
 [4]: https://wp-archive.baka.li/2018/03/ping-qq-baidu-2.png
 [5]: https://wp-archive.baka.li/2018/04/b350m-bios-cpu-oc.jpg
 [6]: https://wp-archive.baka.li/2018/04/B350M-BIOS-2018-03.png