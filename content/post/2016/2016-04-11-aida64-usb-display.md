---
title: 数码相框改造 PC 硬件资源监视器
author: 炒土豆丝
type: post
date: 2016-04-11T15:17:44+00:00
url: /aida64-usb-display/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 11318
dsq_thread_id:
  - 4739617439
views:
  - 1238
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
  - Windows

---
最近逛 NAS 论坛发现个有趣的东西，用于显示硬件资源信息的数码相框。

因为淘宝突然出现了一批 AX206 主控的 2.4 寸数码相框，刷一下固件就变成一个 USB 显示器了，这样在 Windows 设备上就可以通过 Aida64 输出硬件信息到 USB 显示器（数码相框）上，在 Linux 设备（NAS、路由器等）上可以通过&nbsp;LCD4linux 输出，Aida64 有图形化的配置界面，折腾起来方便很多。

<a href="https://item.taobao.com/item.htm?spm=a1z09.2.0.0.uObntS&id=528645541681&_u=b1pv401q5d48" target="_blank" rel="noopener">2.4寸数码相框 openwrt路由器显示设备 LCD2USB USB2LCD AX206 （淘宝）</a>

<a href="http://pan.baidu.com/s/1dFI00Hb" target="_blank" rel="noopener">AX206量产工具、固件和驱动</a>

原价 25 块一个，买了两个 40 块包邮，配件是一条 Mini USB 线和两节七号电池，用 USB 供电下不需要电池。

<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    1.打开AX206_HW_Bootflasher 量产工具压缩包里面的 ProgSPI.exe 文件。<br />2.按住相框正面 M 按钮，然后将相框用 USB 数据线与电脑相连。<br />3.ProgSPI.exe 软件界面现在1个绿色的图标。点软件界面 Browse 按钮 浏览固件文件 fw_pt824_2[竖屏按钮正常].bin 。<br />4.点击右下角 Execute 按钮，写入固件。<br />5.相框自动重启后就完成了。
  </p>
</blockquote>

直接抄卖家的教程，很简单。

<span style="color: #ff0000;">* 如果&nbsp;ax206_lcd_driver.zip 的驱动无法安装，下载&nbsp;<a href="http://pan.baidu.com/s/1eQjAezS" target="_blank" rel="noopener">DPFWIN 整合包</a>&nbsp;，解压，运行&nbsp;USB_Display_Driver 目录下的&nbsp;dpscat.exe ，再运行&nbsp;dpinst64.exe 或者&nbsp;dpinst32.exe 安装驱动。</span>

然后就可以打开 Aida64 配置了，在 设置 的 LCD 项里面启用 AX206 LCD 支持就可以了，接着就调整要输出的信息，还可以自定义背景图片，这个也很简单就是要稍微花点时间，只有在运行着 Aida64 的情况下才有信号输出，所以要把 Aida64 设置为开机启动。

[<img loading="lazy" decoding="async" width="1042" height="637" src="https://wp-archive.baka.li/2016/04/aida64-lcd.png" alt="" class="wp-image-4820" srcset="https://wp-archive.baka.li/2016/04/aida64-lcd.png 1042w, https://wp-archive.baka.li/2016/04/aida64-lcd-150x92.png 150w, https://wp-archive.baka.li/2016/04/aida64-lcd-300x183.png 300w, https://wp-archive.baka.li/2016/04/aida64-lcd-768x469.png 768w, https://wp-archive.baka.li/2016/04/aida64-lcd-1024x626.png 1024w" sizes="(max-width: 1042px) 100vw, 1042px" />][1] 

最后，效果图，电脑关机或者 Aida64 被关闭时数码相框会熄灭。

[<img loading="lazy" decoding="async" width="968" height="1280" src="https://wp-archive.baka.li/2016/04/ax206-usb-display.jpg" alt="" class="wp-image-4821" srcset="https://wp-archive.baka.li/2016/04/ax206-usb-display.jpg 968w, https://wp-archive.baka.li/2016/04/ax206-usb-display-113x150.jpg 113w, https://wp-archive.baka.li/2016/04/ax206-usb-display-227x300.jpg 227w, https://wp-archive.baka.li/2016/04/ax206-usb-display-768x1016.jpg 768w, https://wp-archive.baka.li/2016/04/ax206-usb-display-774x1024.jpg 774w" sizes="(max-width: 968px) 100vw, 968px" />][2]

 [1]: https://wp-archive.baka.li/2016/04/aida64-lcd.png
 [2]: https://wp-archive.baka.li/2016/04/ax206-usb-display.jpg