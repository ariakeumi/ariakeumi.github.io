---
title: Intel Atom D510MO 黑群晖系统
author: 炒土豆丝
type: post
date: 2015-04-08T12:19:32+00:00
url: /intel-atom-d510mo-nas/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 6671
dsq_thread_id:
  - 3975481090
views:
  - 1092
categories:
  - it
tags:
  - NAS
  - 黑群晖

---
GTA5开始了预下载，游戏总量达到恐怖的62GB，128GB的SSD肯定是放不下的了。

为了GTA5，决定升级下NAS，之前的D410平台的NAS是百兆板载网卡的，加了独立网卡就不能使用网络唤醒了，唯有升级板载千兆网卡的。

于是找到了这块Intel原厂的D510MO，在淘宝170块购入二手。

## <a href="http://ark.intel.com/zh-cn/products/42645/Intel-Desktop-Board-D510MO" target="_blank">Intel® Desktop Board D510MO</a>

相比D410，D510的频率不变，但是升级为了双核四线程了，L2缓存也变成了1MB，TDP又10W涨到了13W。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3664" src="https://wp-archive.baka.li/2015/04/intel-atom-d510.png" alt="intel-atom-d510" width="754" height="657" srcset="https://wp-archive.baka.li/2015/04/intel-atom-d510.png 754w, https://wp-archive.baka.li/2015/04/intel-atom-d510-150x131.png 150w, https://wp-archive.baka.li/2015/04/intel-atom-d510-300x261.png 300w" sizes="(max-width: 754px) 100vw, 754px" />][1]

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3665" src="https://wp-archive.baka.li/2015/04/intel-atom-d510mo-1.jpg" alt="intel-atom-d510mo-1" width="1440" height="960" srcset="https://wp-archive.baka.li/2015/04/intel-atom-d510mo-1.jpg 1440w, https://wp-archive.baka.li/2015/04/intel-atom-d510mo-1-150x100.jpg 150w, https://wp-archive.baka.li/2015/04/intel-atom-d510mo-1-300x200.jpg 300w, https://wp-archive.baka.li/2015/04/intel-atom-d510mo-1-1024x683.jpg 1024w" sizes="(max-width: 1440px) 100vw, 1440px" />][2]

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3667" src="https://wp-archive.baka.li/2015/04/intel-atom-d510mo-21.jpg" alt="intel-atom-d510mo-2" width="1440" height="960" srcset="https://wp-archive.baka.li/2015/04/intel-atom-d510mo-21.jpg 1440w, https://wp-archive.baka.li/2015/04/intel-atom-d510mo-21-150x100.jpg 150w, https://wp-archive.baka.li/2015/04/intel-atom-d510mo-21-300x200.jpg 300w, https://wp-archive.baka.li/2015/04/intel-atom-d510mo-21-1024x683.jpg 1024w" sizes="(max-width: 1440px) 100vw, 1440px" />][3]

升级后读取&写入速度得到巨大提升，稳定100MB/s左右。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3682" src="https://wp-archive.baka.li/2015/04/Intel-d510mo-3.png" alt="Intel-d510mo-3" width="463" height="302" srcset="https://wp-archive.baka.li/2015/04/Intel-d510mo-3.png 463w, https://wp-archive.baka.li/2015/04/Intel-d510mo-3-150x98.png 150w, https://wp-archive.baka.li/2015/04/Intel-d510mo-3-300x196.png 300w" sizes="(max-width: 463px) 100vw, 463px" />][4] [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3683" src="https://wp-archive.baka.li/2015/04/Intel-d510mo-4.png" alt="Intel-d510mo-4" width="463" height="302" srcset="https://wp-archive.baka.li/2015/04/Intel-d510mo-4.png 463w, https://wp-archive.baka.li/2015/04/Intel-d510mo-4-150x98.png 150w, https://wp-archive.baka.li/2015/04/Intel-d510mo-4-300x196.png 300w" sizes="(max-width: 463px) 100vw, 463px" />][5]

[divider type=&#8221;white|thin|thick|short|dotted|dashed&#8221; spacing=&#8221;10&#8243;]

## <a title="WIKI" href="http://zh.wikipedia.org/wiki/ISCSI" target="_blank">iSCSI</a>

游戏不能安装在NAS映射的网络驱动器上，这时候就需要用到“ISCSI”了，建立一个iSCSI分卷可以最大程度的模拟本地硬盘，也就可以安装运行各种游戏了。

打开DSM系统的“存储空间管理员”的“iSCSI LUN”项，点击“新增”，选择“iSCSI（一般文件）”，下一步。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3668" src="https://wp-archive.baka.li/2015/04/ISCSI-1.png" alt="ISCSI-1" width="963" height="601" srcset="https://wp-archive.baka.li/2015/04/ISCSI-1.png 963w, https://wp-archive.baka.li/2015/04/ISCSI-1-150x94.png 150w, https://wp-archive.baka.li/2015/04/ISCSI-1-300x187.png 300w, https://wp-archive.baka.li/2015/04/ISCSI-1-400x250.png 400w" sizes="(max-width: 963px) 100vw, 963px" />][6]

设置容量，后期是可以修改的。[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3669" src="https://wp-archive.baka.li/2015/04/ISCSI-2.png" alt="ISCSI-2" width="962" height="600" srcset="https://wp-archive.baka.li/2015/04/ISCSI-2.png 962w, https://wp-archive.baka.li/2015/04/ISCSI-2-150x94.png 150w, https://wp-archive.baka.li/2015/04/ISCSI-2-300x187.png 300w, https://wp-archive.baka.li/2015/04/ISCSI-2-400x250.png 400w" sizes="(max-width: 962px) 100vw, 962px" />][7] [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3670" src="https://wp-archive.baka.li/2015/04/ISCSI-3.png" alt="ISCSI-3" width="966" height="603" srcset="https://wp-archive.baka.li/2015/04/ISCSI-3.png 966w, https://wp-archive.baka.li/2015/04/ISCSI-3-150x94.png 150w, https://wp-archive.baka.li/2015/04/ISCSI-3-300x187.png 300w, https://wp-archive.baka.li/2015/04/ISCSI-3-400x250.png 400w" sizes="(max-width: 966px) 100vw, 966px" />][8] [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3671" src="https://wp-archive.baka.li/2015/04/ISCSI-4.png" alt="ISCSI-4" width="966" height="603" srcset="https://wp-archive.baka.li/2015/04/ISCSI-4.png 966w, https://wp-archive.baka.li/2015/04/ISCSI-4-150x94.png 150w, https://wp-archive.baka.li/2015/04/ISCSI-4-300x187.png 300w, https://wp-archive.baka.li/2015/04/ISCSI-4-400x250.png 400w" sizes="(max-width: 966px) 100vw, 966px" />][9] [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3672" src="https://wp-archive.baka.li/2015/04/ISCSI-5.png" alt="ISCSI-5" width="964" height="602" srcset="https://wp-archive.baka.li/2015/04/ISCSI-5.png 964w, https://wp-archive.baka.li/2015/04/ISCSI-5-150x94.png 150w, https://wp-archive.baka.li/2015/04/ISCSI-5-300x187.png 300w, https://wp-archive.baka.li/2015/04/ISCSI-5-400x250.png 400w" sizes="(max-width: 964px) 100vw, 964px" />][10]

完成后打开“iSCSI发起程序”。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3673" src="https://wp-archive.baka.li/2015/04/ISCSI-6.png" alt="ISCSI-6" width="1049" height="767" srcset="https://wp-archive.baka.li/2015/04/ISCSI-6.png 1049w, https://wp-archive.baka.li/2015/04/ISCSI-6-150x110.png 150w, https://wp-archive.baka.li/2015/04/ISCSI-6-300x219.png 300w, https://wp-archive.baka.li/2015/04/ISCSI-6-1024x749.png 1024w" sizes="(max-width: 1049px) 100vw, 1049px" />][11]

点击“发现”项的“发现门户”。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3674" src="https://wp-archive.baka.li/2015/04/ISCSI-7.png" alt="ISCSI-7" width="497" height="670" srcset="https://wp-archive.baka.li/2015/04/ISCSI-7.png 497w, https://wp-archive.baka.li/2015/04/ISCSI-7-111x150.png 111w, https://wp-archive.baka.li/2015/04/ISCSI-7-223x300.png 223w" sizes="(max-width: 497px) 100vw, 497px" />][12]

输入NAS的IP地址，端口默认。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3675" src="https://wp-archive.baka.li/2015/04/ISCSI-8.png" alt="ISCSI-8" width="497" height="670" srcset="https://wp-archive.baka.li/2015/04/ISCSI-8.png 497w, https://wp-archive.baka.li/2015/04/ISCSI-8-111x150.png 111w, https://wp-archive.baka.li/2015/04/ISCSI-8-223x300.png 223w" sizes="(max-width: 497px) 100vw, 497px" />][13]

然后连接。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3676" src="https://wp-archive.baka.li/2015/04/ISCSI-9.png" alt="ISCSI-9" width="497" height="670" srcset="https://wp-archive.baka.li/2015/04/ISCSI-9.png 497w, https://wp-archive.baka.li/2015/04/ISCSI-9-111x150.png 111w, https://wp-archive.baka.li/2015/04/ISCSI-9-223x300.png 223w" sizes="(max-width: 497px) 100vw, 497px" />][14]

打开Windows的磁盘管理，初始化磁盘后建立分区就有了一个新的本地磁盘。[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3677" src="https://wp-archive.baka.li/2015/04/ISCSI-10.png" alt="ISCSI-10" width="640" height="452" srcset="https://wp-archive.baka.li/2015/04/ISCSI-10.png 640w, https://wp-archive.baka.li/2015/04/ISCSI-10-150x106.png 150w, https://wp-archive.baka.li/2015/04/ISCSI-10-300x212.png 300w" sizes="(max-width: 640px) 100vw, 640px" />][15]

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3679" src="https://wp-archive.baka.li/2015/04/iSCSI-11.png" alt="iSCSI-11" width="1049" height="800" srcset="https://wp-archive.baka.li/2015/04/iSCSI-11.png 1049w, https://wp-archive.baka.li/2015/04/iSCSI-11-150x114.png 150w, https://wp-archive.baka.li/2015/04/iSCSI-11-300x229.png 300w, https://wp-archive.baka.li/2015/04/iSCSI-11-1024x781.png 1024w" sizes="(max-width: 1049px) 100vw, 1049px" />][16]

大功告成，挂机下载GTA。[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3680" src="https://wp-archive.baka.li/2015/04/steam-gta5-download.jpg" alt="steam-gta5-download" width="1920" height="1080" srcset="https://wp-archive.baka.li/2015/04/steam-gta5-download.jpg 1920w, https://wp-archive.baka.li/2015/04/steam-gta5-download-150x84.jpg 150w, https://wp-archive.baka.li/2015/04/steam-gta5-download-300x169.jpg 300w, https://wp-archive.baka.li/2015/04/steam-gta5-download-1024x576.jpg 1024w" sizes="(max-width: 1920px) 100vw, 1920px" />][17]

 [1]: https://wp-archive.baka.li/2015/04/intel-atom-d510.png
 [2]: https://wp-archive.baka.li/2015/04/intel-atom-d510mo-1.jpg
 [3]: https://wp-archive.baka.li/2015/04/intel-atom-d510mo-21.jpg
 [4]: https://wp-archive.baka.li/2015/04/Intel-d510mo-3.png
 [5]: https://wp-archive.baka.li/2015/04/Intel-d510mo-4.png
 [6]: https://wp-archive.baka.li/2015/04/ISCSI-1.png
 [7]: https://wp-archive.baka.li/2015/04/ISCSI-2.png
 [8]: https://wp-archive.baka.li/2015/04/ISCSI-3.png
 [9]: https://wp-archive.baka.li/2015/04/ISCSI-4.png
 [10]: https://wp-archive.baka.li/2015/04/ISCSI-5.png
 [11]: https://wp-archive.baka.li/2015/04/ISCSI-6.png
 [12]: https://wp-archive.baka.li/2015/04/ISCSI-7.png
 [13]: https://wp-archive.baka.li/2015/04/ISCSI-8.png
 [14]: https://wp-archive.baka.li/2015/04/ISCSI-9.png
 [15]: https://wp-archive.baka.li/2015/04/ISCSI-10.png
 [16]: https://wp-archive.baka.li/2015/04/iSCSI-11.png
 [17]: https://wp-archive.baka.li/2015/04/steam-gta5-download.jpg