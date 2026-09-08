---
title: 'SONY Xperia Z3C 升级 Android 5.1.1 保留 ROOT & REC'
author: 炒土豆丝
type: post
date: 2015-08-02T18:29:58+00:00
url: /sony-xperia-z3c-android-5-1-1-root-rec/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 5600
dsq_thread_id:
  - 3997354195
views:
  - 769
categories:
  - it
tags:
  - Android
  - SONY
  - 手机

---
最近 Z3C 收到了 Android 5.1.1 的 OTA ，因为手机已 ROOT ，无法验证，只能通过卡刷的方式更新，这样才可以保留 ROOT 和 REC 。

<span style="color: #99cc00;">5.1.1 是个很重要的版本，该版本修复了 Lollipop 固件中的内存泄漏 Bug ，在 Android M 还没着落的时候还是先刷上 5.1 先吧。</span>

索尼的手机折腾起来真的挺麻烦的，ROOT 和 REC 什么的。

不打算写详细的教程，汇总下需要的教程再整理下过程。

**<span style="color: #ff0000;">* 在升级之前请备份手机的重要数据</span>**

  * 4.4.4 和 5.0.2 固件的先 ROOT 和刷入 REC ，如果当前固件没有合适的 ROOT 工具，先用&nbsp;FlashTool&nbsp;强刷到合适的版本。

4.4 &nbsp;ROOT ：[XDA|Z3/Z3C免解锁ROOT|一键ROOT与REC工具|giefroot_v3定制版][1]{#thread_subject}

5.0 ROOT ：<a href="http://bonnieee.co/2464/root-xperia-lollipop" target="_blank">懶人式一鍵ROOT工具 – Xperia Lollipop 5.0專用</a>

FlashTool 下载：<a href="http://bbs.gfan.com/android-8036255-1-1.html" target="_blank">索尼Xperia手机刷机工具 <span class="cred">FlashTool</span> 0.9.19.0 汉化优化版</a>

强刷教程：<a href="http://www.anqu.com/study_621/51327/" target="_blank">索尼Xperia系列Flashtool强刷图文教程</a>

强刷驱动问题：<a href="http://tieba.baidu.com/p/2227615547" target="_blank">解决windows8下不能安装flashtool+fastboot驱动问题</a>

  * 下载带 ROOT 和 REC 的 5.1.1 固件卡刷包，进入 REC 三清 Wipe 再刷入，然后关机。

[索尼5.1 Z3C 带最新root和rec卡刷包][2]{#thread_subject}

  * 下载 5.1.1 的官方固件然后强刷 5.1.1 的官方固件内核。

<p id="_disk_id_23">
  <a href="http://pan.baidu.com/s/1hUb0q" target="_blank">Z3C 5.1.1 官方固件（D5803 23.4.A.0.546 Customized BAL）</a>
</p>

[z3c刷完5.1.1无限重启的的进，你们需要关机强刷下对应的内核][3]{#thread_subject}

官方版的 Xposed 框架暂时还不支持 Android 5.1 ，可以刷其他大牛制作的。

下载下面链接里面的 <a href="http://forum.xda-developers.com/attachment.php?s=65a46e13099e0be34f24bc4db90e1efe&attachmentid=3420636&d=1438030312" target="_blank">posed-v68-sdk22-arm-by-romracer</a> 在 REC 刷入，再安装 Xposed Installer（3.0 alpha4 ），64位手机下载 arm64 的。

## <a href="http://forum.xda-developers.com/xposed/super-alpha-posted-permission-xposed-t3072979" target="_blank">Xposed for Android 5.1 &#8211; v68 / 20150727 / SDK22</a>

经过以上多番折腾，手机终于可以愉快的使用了。

5.1.1 固件相比之前&nbsp;5.0.2 流畅了不少，还有个小变化，下拉菜单可以直接连接 WIFI 或者蓝牙而不用跳转设置。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4444" src="https://wp-archive.baka.li/2015/08/sony-xperia-5.1.1.png" alt="sony-xperia-5.1.1" width="450" height="720" srcset="https://wp-archive.baka.li/2015/08/sony-xperia-5.1.1.png 450w, https://wp-archive.baka.li/2015/08/sony-xperia-5.1.1-94x150.png 94w, https://wp-archive.baka.li/2015/08/sony-xperia-5.1.1-188x300.png 188w" sizes="(max-width: 450px) 100vw, 450px" />][4]

 [1]: http://bbs.gfan.com/android-7829711-1-1.html
 [2]: http://bbs.gfan.com/android-8026444-1-1.html
 [3]: http://bbs.gfan.com/android-8027318-1-1.html
 [4]: https://wp-archive.baka.li/2015/08/sony-xperia-5.1.1.png