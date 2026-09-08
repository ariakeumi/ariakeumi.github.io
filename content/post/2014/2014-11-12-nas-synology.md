---
title: 炒土豆丝の黑群晖 NAS
author: 炒土豆丝
type: post
date: 2014-11-12T12:13:20+00:00
url: /nas-synology/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 6855
dsq_thread_id:
  - 3975480158
views:
  - 805
categories:
  - it
tags:
  - NAS
  - PC

---
10月的时候就打算买一台群晖的NAS了，结果被人忽悠去买iPad了。这个月又有双十一&#8230;没钱了，没办法了不能再拖了只好装一台黑群晖了。

之前在SMZDM（色魔张大妈）看到这两篇这样的文章：

## <a title="跳转" href="http://show.smzdm.com/detail/43425" target="_blank">500元 NAS 黑群晖 配置完成（不含硬盘），NAS能做什么？</a> {.article_title}

## <a href="http://jy.smzdm.com/detail/20115" target="_blank">NAS群晖DSM 5.0-4458 傻瓜安装教程</a> {.article_title}

正好机箱、电源我都有了，可以更低价搞一个。

于是，买了富士康的嵌入式CPU的ITX板子（Intel Atom D410、130块），1GB DDR2内存（10块），一张螃蟹千兆网卡（10块），一个U盘（15块），加上已有的电源和机箱，花了183块就搞定了一台黑群晖，配件虽然都是拆机的古董，但是性能比1500块DS213J强。

到手后我才想起来，这货只有两个SATA啊！嘛，算了，正好阻止了以后买硬盘。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3223" src="https://wp-archive.baka.li/2014/11/FOX-ATOM-D410-MB.jpg" alt="FOX-ATOM-D410-MB" width="850" height="960" srcset="https://wp-archive.baka.li/2014/11/FOX-ATOM-D410-MB.jpg 850w, https://wp-archive.baka.li/2014/11/FOX-ATOM-D410-MB-132x150.jpg 132w, https://wp-archive.baka.li/2014/11/FOX-ATOM-D410-MB-265x300.jpg 265w" sizes="(max-width: 850px) 100vw, 850px" />][1]

问别人借的两个蓝盘备份数据，因为群晖的DSM系统使用linux的ext4文件系统，所以安装DSM后需要格式化磁盘。

最后只备份了不到200GB数据就急忙装上了&#8230;

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3225" src="https://wp-archive.baka.li/2014/11/WD-BULE-X2.jpg" alt="WD-BULE-X2" width="1280" height="956" srcset="https://wp-archive.baka.li/2014/11/WD-BULE-X2.jpg 1280w, https://wp-archive.baka.li/2014/11/WD-BULE-X2-150x112.jpg 150w, https://wp-archive.baka.li/2014/11/WD-BULE-X2-300x224.jpg 300w, https://wp-archive.baka.li/2014/11/WD-BULE-X2-1024x764.jpg 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][2]

装好后直接启动，到这里的时候去PC端安装DSM系统。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3226" src="https://wp-archive.baka.li/2014/11/DSM-BOOT.jpg" alt="DSM-BOOT" width="1280" height="956" srcset="https://wp-archive.baka.li/2014/11/DSM-BOOT.jpg 1280w, https://wp-archive.baka.li/2014/11/DSM-BOOT-150x112.jpg 150w, https://wp-archive.baka.li/2014/11/DSM-BOOT-300x224.jpg 300w, https://wp-archive.baka.li/2014/11/DSM-BOOT-1024x764.jpg 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][3]

使用Synology Assistant找到局域网的黑群晖来安装DSM系统，DSM系统是需要通过pat后辍名的文件安装，可以通过官网下载到。

## <a title="FTP下载" href="http://ukdl.synology.com/ftp/DSM/5.0/4493/" target="_blank">Index of /ftp/DSM/5.0/4493</a>

## [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3227" src="https://wp-archive.baka.li/2014/11/DSM-1.png" alt="DSM-1" width="696" height="608" srcset="https://wp-archive.baka.li/2014/11/DSM-1.png 696w, https://wp-archive.baka.li/2014/11/DSM-1-150x131.png 150w, https://wp-archive.baka.li/2014/11/DSM-1-300x262.png 300w" sizes="(max-width: 696px) 100vw, 696px" />][4]

中间再设置NAS名称、密码等。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3228" src="https://wp-archive.baka.li/2014/11/DSM-2.png" alt="DSM-2" width="802" height="632" srcset="https://wp-archive.baka.li/2014/11/DSM-2.png 802w, https://wp-archive.baka.li/2014/11/DSM-2-150x118.png 150w, https://wp-archive.baka.li/2014/11/DSM-2-300x236.png 300w" sizes="(max-width: 802px) 100vw, 802px" />][5]

很快就装好了，然后通过浏览器登陆。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3229" src="https://wp-archive.baka.li/2014/11/DSM-3.jpg" alt="DSM-3" width="483" height="426" srcset="https://wp-archive.baka.li/2014/11/DSM-3.jpg 483w, https://wp-archive.baka.li/2014/11/DSM-3-150x132.jpg 150w, https://wp-archive.baka.li/2014/11/DSM-3-300x264.jpg 300w" sizes="(max-width: 483px) 100vw, 483px" />][6]

DSM系统很像Windows 7，窗口预览、多任务切换、桌面小工具什么的。

设置什么的就不写了，网上教程很多。

安装套件能实现各种功能。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3230" src="https://wp-archive.baka.li/2014/11/DSM-4.jpg" alt="DSM-4" width="1280" height="702" srcset="https://wp-archive.baka.li/2014/11/DSM-4.jpg 1280w, https://wp-archive.baka.li/2014/11/DSM-4-150x82.jpg 150w, https://wp-archive.baka.li/2014/11/DSM-4-300x164.jpg 300w, https://wp-archive.baka.li/2014/11/DSM-4-1024x561.jpg 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][7]

<!--more-->

因为是黑群晖的原因，型号被识别位DS3612xs，CPU&#8230;i3&#8230;

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3232" src="https://wp-archive.baka.li/2014/11/DSM-6.png" alt="DSM-6" width="995" height="571" srcset="https://wp-archive.baka.li/2014/11/DSM-6.png 995w, https://wp-archive.baka.li/2014/11/DSM-6-150x86.png 150w, https://wp-archive.baka.li/2014/11/DSM-6-300x172.png 300w" sizes="(max-width: 995px) 100vw, 995px" />][8]

拷贝速度，最多只有64MB/s，不知道什么原因，网卡、网线、路由都是千兆的。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3231" src="https://wp-archive.baka.li/2014/11/DSM-5.png" alt="DSM-5" width="452" height="307" srcset="https://wp-archive.baka.li/2014/11/DSM-5.png 452w, https://wp-archive.baka.li/2014/11/DSM-5-150x101.png 150w, https://wp-archive.baka.li/2014/11/DSM-5-300x203.png 300w" sizes="(max-width: 452px) 100vw, 452px" />][9]

下载管理，支持迅雷离线，百度云的内容也可以下载，不过要先提取正确的链接。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3236" src="https://wp-archive.baka.li/2014/11/DSM-DOWNLOAD.png" alt="DSM-DOWNLOAD" width="982" height="582" srcset="https://wp-archive.baka.li/2014/11/DSM-DOWNLOAD.png 982w, https://wp-archive.baka.li/2014/11/DSM-DOWNLOAD-150x88.png 150w, https://wp-archive.baka.li/2014/11/DSM-DOWNLOAD-300x177.png 300w" sizes="(max-width: 982px) 100vw, 982px" />][10]

磁盘映射。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3240" src="https://wp-archive.baka.li/2014/11/DSM-7.png" alt="DSM-7" width="827" height="288" srcset="https://wp-archive.baka.li/2014/11/DSM-7.png 827w, https://wp-archive.baka.li/2014/11/DSM-7-150x52.png 150w, https://wp-archive.baka.li/2014/11/DSM-7-300x104.png 300w" sizes="(max-width: 827px) 100vw, 827px" />][11]

Android的DS File文件管理APP，遵循Android Design规范，业界良心。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3233" src="https://wp-archive.baka.li/2014/11/DSM-FILE-APP.png" alt="DSM-FILE-APP" width="432" height="720" srcset="https://wp-archive.baka.li/2014/11/DSM-FILE-APP.png 768w, https://wp-archive.baka.li/2014/11/DSM-FILE-APP-90x150.png 90w, https://wp-archive.baka.li/2014/11/DSM-FILE-APP-180x300.png 180w, https://wp-archive.baka.li/2014/11/DSM-FILE-APP-614x1024.png 614w" sizes="(max-width: 432px) 100vw, 432px" />][12]

iOS的DS Photo+相册APP，再iOS中截图完成后通过这个APP上传图片然后在PC的资源管理器中打开路径上传到此篇文章上，方便。

打算把各种同人志漫画资源也扔到相册目录然后通过DS Photo+看，节省iPad的存储空间。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3241" src="https://wp-archive.baka.li/2014/11/DSM-PHOTO-.jpg" alt="DSM-PHOTO+" width="1280" height="960" srcset="https://wp-archive.baka.li/2014/11/DSM-PHOTO-.jpg 1280w, https://wp-archive.baka.li/2014/11/DSM-PHOTO--150x112.jpg 150w, https://wp-archive.baka.li/2014/11/DSM-PHOTO--300x225.jpg 300w, https://wp-archive.baka.li/2014/11/DSM-PHOTO--1024x768.jpg 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][13]

通过小米盒子访问。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3242" src="https://wp-archive.baka.li/2014/11/DSM-8.jpg" alt="DSM-8" width="1280" height="956" srcset="https://wp-archive.baka.li/2014/11/DSM-8.jpg 1280w, https://wp-archive.baka.li/2014/11/DSM-8-150x112.jpg 150w, https://wp-archive.baka.li/2014/11/DSM-8-300x224.jpg 300w, https://wp-archive.baka.li/2014/11/DSM-8-1024x764.jpg 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][14]

还有好多功能没玩，累死了，不能再写了。

电源声音有点吵，打算以后换个DC电源和1U机箱。

参考资料：

<a title="跳转" href="http://show.smzdm.com/detail/43425" target="_blank">500元 NAS 黑群晖 配置完成（不含硬盘），NAS能做什么？</a>

<a href="http://jy.smzdm.com/detail/20115" target="_blank">NAS群晖DSM 5.0-4458 傻瓜安装教程</a>

<a href="http://www.chiphell.com/thread-580014-1-1.html" target="_blank">【DSM全阶段教程】-索引贴</a>

[一步一步建立自己的黑群晖][15]{#thread_subject}

 [1]: https://wp-archive.baka.li/2014/11/FOX-ATOM-D410-MB.jpg
 [2]: https://wp-archive.baka.li/2014/11/WD-BULE-X2.jpg
 [3]: https://wp-archive.baka.li/2014/11/DSM-BOOT.jpg
 [4]: https://wp-archive.baka.li/2014/11/DSM-1.png
 [5]: https://wp-archive.baka.li/2014/11/DSM-2.png
 [6]: https://wp-archive.baka.li/2014/11/DSM-3.jpg
 [7]: https://wp-archive.baka.li/2014/11/DSM-4.jpg
 [8]: https://wp-archive.baka.li/2014/11/DSM-6.png
 [9]: https://wp-archive.baka.li/2014/11/DSM-5.png
 [10]: https://wp-archive.baka.li/2014/11/DSM-DOWNLOAD.png
 [11]: https://wp-archive.baka.li/2014/11/DSM-7.png
 [12]: https://wp-archive.baka.li/2014/11/DSM-FILE-APP.png
 [13]: https://wp-archive.baka.li/2014/11/DSM-PHOTO-.jpg
 [14]: https://wp-archive.baka.li/2014/11/DSM-8.jpg
 [15]: http://www.gebi1.com/thread-235173-1-1.html