---
title: 守望先锋闪退，元凶居然是。。。插排/插线板/插座！！！
author: 炒土豆丝
type: post
date: 2017-07-10T12:55:25+00:00
url: /overwatch-shutdown/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 3979
dsq_thread_id:
  - 5976398112
views:
  - 838
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
        https://wp-archive.baka.li/2017/07/overwatch-shutdown.mp4
        5891631
        video/mp4
        
categories:
  - ACG
  - it
tags:
  - 守望先锋
  - 显卡
  - 游戏

---
 

沉迷守望先锋，半年没更博，这次更也是因为玩游戏的时候遇到怪事了。

从半个月前起，在天梯比赛中，经常出现游戏闪退现象，让我损失了很多竞技分，还坑了不少队友，在这里说声抱歉，我也很绝望啊。

闪退多次，总结出了一点规律：玩源氏的时候闪退几率特别高，比其它英雄多得多，闪退后回到桌面鼠标指针会消失几秒。<figure class="wp-block-video"><video controls src="https://wp-archive.baka.li/2017/07/overwatch-shutdown.mp4"></video> 

照常理来说，游戏闪退首要背锅的是显卡驱动，为此，我安装了无数个版本的N卡驱动，依旧闪退。接着，又想着我的 Windows 10 更新了创意者版本，因为删掉了旧系统备份，重新安装了老版本的 Windows 10，还是闪退 ，这里提醒大家系统更新大版本要保留一下备份。

用 Windows 7 ？闪退。

重新安装游戏？闪退。

按暴雪官方客服说的修复游戏？闪退。

没办法，只能怀疑硬件了。之前因为水冷漏液(九州风神船长120EX)，我的 GTX 970 显卡差点遭殃，因此怀疑是漏液导致显卡内伤暗病。

[<img loading="lazy" decoding="async" width="900" height="506" src="https://wp-archive.baka.li/2017/09/overwatch-shutdown-GTX970.jpg" alt="" class="wp-image-4876" srcset="https://wp-archive.baka.li/2017/09/overwatch-shutdown-GTX970.jpg 900w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-GTX970-150x84.jpg 150w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-GTX970-300x169.jpg 300w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-GTX970-768x432.jpg 768w" sizes="(max-width: 900px) 100vw, 900px" />][1] 

但是经过 Aida64 、3DMark 、Furmark 的疯狂烤机测试，显卡似乎没问题，GTA 5 等游戏里也正常啊。

且慢！经过细心观察，我发现，这张 Boost 频率 1197 MHz 的 GTX 970 在游戏里面居然运行在 1265 MHz 的频率上。

信心满满的我下载了微星的显卡超频软件 MSI Afterburne 对显卡进行手动降频。

[<img loading="lazy" decoding="async" width="400" height="494" src="https://wp-archive.baka.li/2017/09/overwatch-shutdown-GPUZ.png" alt="" class="wp-image-4875" srcset="https://wp-archive.baka.li/2017/09/overwatch-shutdown-GPUZ.png 400w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-GPUZ-121x150.png 121w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-GPUZ-243x300.png 243w" sizes="(max-width: 400px) 100vw, 400px" />][2] 

结果它还是闪退了！(PS：显卡的运行频率都是高于标称频率的)

最近天气高温，会不会显卡太热了才出现问题？

不是，拆开机箱侧板，把显卡风扇调到 100% 转速，让它始终在 60° 左右运行，还是闪退。

实在没办法，痛下苦心买了张 EVGA 1070 FTW (因为挖矿潮，贵了很多)，结果还他妈闪退。

绝望的我搜了很多关于闪退的帖子，从电源到CPU，内存到散热，全部都怀疑了一遍。

在 NGA 帖子 守望先锋闪退！到底谁的锅？ 里一个不起眼的楼层看到这样一条回复：

[<img loading="lazy" decoding="async" width="676" height="406" src="https://wp-archive.baka.li/2017/09/overwatch-shutdown-NGA.png" alt="" class="wp-image-4877" srcset="https://wp-archive.baka.li/2017/09/overwatch-shutdown-NGA.png 676w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-NGA-150x90.png 150w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-NGA-300x180.png 300w" sizes="(max-width: 676px) 100vw, 676px" />][3] 

换了插排就不闪退了？怎么跟 HiFi 玄学一样？

抱着死马当活马医的心态，我给电脑主机的插头从插排的一端换到另一端，在靶场狂砍5分钟，真的没闪退(我的插排是 MAYA 的，质量应该没问题的)。

换回原来的插头位置，两分钟马上闪退。

什么原理也不清楚，反正可以愉快玩游戏了。

[<img loading="lazy" decoding="async" width="400" height="424" src="https://wp-archive.baka.li/2017/09/overwatch-shutdown-OMG.jpg" alt="" class="wp-image-4878" srcset="https://wp-archive.baka.li/2017/09/overwatch-shutdown-OMG.jpg 400w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-OMG-142x150.jpg 142w, https://wp-archive.baka.li/2017/09/overwatch-shutdown-OMG-283x300.jpg 283w" sizes="(max-width: 400px) 100vw, 400px" />][4]

 [1]: https://wp-archive.baka.li/2017/09/overwatch-shutdown-GTX970.jpg
 [2]: https://wp-archive.baka.li/2017/09/overwatch-shutdown-GPUZ.png
 [3]: https://wp-archive.baka.li/2017/09/overwatch-shutdown-NGA.png
 [4]: https://wp-archive.baka.li/2017/09/overwatch-shutdown-OMG.jpg