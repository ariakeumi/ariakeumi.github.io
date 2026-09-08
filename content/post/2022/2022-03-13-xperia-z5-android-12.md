---
title: 给2015年的老古董手机刷上 Android 12
author: 炒土豆丝
type: post
date: 2022-03-13T09:51:29+00:00
url: /xperia-z5-android-12/
image: https://wp-archive.baka.li/2022/03/sony-xperia-z5.jpg
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 79
views:
  - 1324
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
  - Android

---
 

抽屉翻出来台 Xperia Z5，发现还能开机用，就打算给它刷个机玩玩。

<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    SONY Xperia Z5 Dual (E6683)
  </p>
  
  <p>
    屏幕 5.2吋、1920×1080分辨率（FULL HD 1080p）
  </p>
  
  <p>
    CPU 高通 Snapdragon 810 2.0GHz八核心
  </p>
  
  <p>
    GPU Adreno 430
  </p>
  
  <p>
    RAM 3 GB LPDDR4
  </p>
  
  <p>
    ROM 32/64 GB
  </p>
  
  <cite>首次发布 2015年9月2日</cite>
</blockquote>

手机目前还是 Android 7.0 的系统，是在机锋上找到的固件，最新的官方固件估计也是 7.0 ，上机锋看看有没有固件发现居然已经关站了？&#8230;

在 XDA 上逛了逛发现已经有了基于 Android 12 的 LineageOS 19.0 第三方固件，不过相机还不能正常工作，先刷这个试试吧。

<a href="https://forum.xda-developers.com/t/rom-12-0-unofficial-lineageos-19-0-sumire-beta.4391657/" target="_blank" rel="noreferrer noopener">[ROM][12.0][UNOFFICIAL] LineageOS 19.0 [sumire] [BETA]</a>

开刷：

## 安装 Fastboot 驱动 

在 <a href="http://www.flashtool.net/downloads_windows.php" target="_blank" rel="noreferrer noopener">Flashtool.net</a> 这网站上下载 Flashtool 工具并解压安装，安装目录里面的 drivers 目录有个驱动程序，运行它安装 Fastboot Drivers 和 Xperia Z5 Drivce Driver。

如果安装过程中出现驱动程序签名错误，你需要关闭 Windows 的驱动程序签名验证，参考下面的方法。

<a href="https://jingyan.baidu.com/article/624e74594dbc8d34e8ba5aa6.html" target="_blank" rel="noreferrer noopener">Win10怎么禁用驱动程序强制签名</a>

## 连接手机 

在系统设置的开发者选项里开启 OEM 解锁和 USB 调试，然后关机，Mrico USB 线连接手机，长按音量+键，USB 线再连接上电脑，手机指示灯会蓝灯常亮。

对了，手机还需要解锁，但是我刚买手机就解锁了，已经忘记怎么操作了，参考下面的其他教程。

<a href="https://www.netded.com/a/jingpinshouji/2016/0709/31817.html" target="_blank" rel="noreferrer noopener">索尼Xperia Z5解锁教程<em>Sony Z5解锁BootLoader</em>获取解锁码 &#8211; 迷你手机网</a>

## 刷入 Recovery 

在 [\[TWRP\]\[Z5\] TWRP 3.2.3 for Xperia Z5, Z5C and Z3+][1] 链接里下载 recovery.img 和 ADB 工具。

把 recovery.img 放到 ADB 目录内，在命令提示符启动，执行下面的命令刷入 Recovery 。

<pre class="wp-block-code"><code>fastboot flash recovery recovery.img</code></pre>

## 刷入 ROM  

关机状态下长按音量-键和电源键，手机震动后松开电源键，过几秒就能进入 Recovery（TWRP） ，TWRP 这个操作就比较简单了。

格式化 data ，再重启进 Recovery ，然后双清 system/data（wipe），刷入刷机包，搞定。

<img loading="lazy" decoding="async" width="960" height="1280" src="https://wp-archive.baka.li/2022/03/xperia-z5-android-12.jpg" alt="" class="wp-image-6013" /> 

 [1]: https://forum.xda-developers.com/t/twrp-z5-twrp-3-2-3-for-xperia-z5-z5c-and-z3.3571050/