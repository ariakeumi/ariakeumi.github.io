---
title: Chromium OS虚拟机体验
author: 炒土豆丝
type: post
date: 2014-03-18T12:28:14+00:00
url: /chromium-os/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 2351
dsq_thread_id:
  - 3975460050
views:
  - 813
categories:
  - it
tags:
  - 虚拟机

---
[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1779" src="https://wp-archive.baka.li/2014/03/Chromium-OS.jpg" alt="Chromium OS" width="1082" height="691" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS.jpg 1082w, https://wp-archive.baka.li/2014/03/Chromium-OS-150x95.jpg 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-300x191.jpg 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-1024x653.jpg 1024w" sizes="(max-width: 1082px) 100vw, 1082px" />][1]

[blockquote source=&#8221;WIKipedia&#8221;]**Google Chrome OS**是由[Google][2]所进行的一项轻型计算机[操作系统][3]发展计划，发展出专用于[互联网][4]的云操作系统。<sup id="cite_ref-PC_World_3-0"><a href="http://zh.wikipedia.org/wiki/Google_Chrome_OS#cite_note-PC_World-3">[3]</a></sup><sup id="cite_ref-4"><a href="http://zh.wikipedia.org/wiki/Google_Chrome_OS#cite_note-4">[4]</a></sup>该操作系统设计计划于2009年7月7日发布，系统植基于[谷歌浏览器][5]及[Linux内核][6]。最初设置在[上网本][7]上使用<sup id="cite_ref-Guardian_5-0"><a href="http://zh.wikipedia.org/wiki/Google_Chrome_OS#cite_note-Guardian-5">[5]</a></sup>，在2011年上半年正式发表上市<sup id="cite_ref-Times_6-0"><a href="http://zh.wikipedia.org/wiki/Google_Chrome_OS#cite_note-Times-6">[6]</a></sup><sup id="cite_ref-7"><a href="http://zh.wikipedia.org/wiki/Google_Chrome_OS#cite_note-7">[7]</a></sup><sup id="cite_ref-8"><a href="http://zh.wikipedia.org/wiki/Google_Chrome_OS#cite_note-8">[8]</a></sup>“Chrome OS”可以在[x86][8]或[ARM][9]两种微处理器上运行。<sup id="cite_ref-Bloomberg_9-0"><a href="http://zh.wikipedia.org/wiki/Google_Chrome_OS#cite_note-Bloomberg-9">[9]</a></sup>。</blockquote> 

<a title="WIKI" href="http://zh.wikipedia.org/wiki/Chromium_OS" target="_blank">Chromium OS</a><span style="font-size: 14px; line-height: 1.5em;">是Chrome OS的开源版本，Chrome OS用于指定的硬件上，所以无法在虚拟机里体验Chrome OS。</span>

我所安装的由国外大神hexxeh所编译的Chromium OS，并不是官方版本。

首先，**<a title="下载" href="http://chromeos.hexxeh.net/" target="_blank">下载 Chromium OS</a>**，这不是一个镜像文件，而是ZIP压缩文件。

因为我用的是**<a title="VM虚拟机" href="http://www.zdfans.com/810.html" target="_blank">VM虚拟机</a>**，所以我下载了VMWare的，解压了就是一个VMDK文件和VMX文件，VMDK是虚拟磁盘，VMX是虚拟机配置文件，直接打开VMX文件就可以开启虚拟机了，根本不需要设置，超级傻瓜。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1772" src="https://wp-archive.baka.li/2014/03/Chromium-OS-DOWN.png" alt="Chromium-OS-DOWN" width="791" height="418" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-DOWN.png 791w, https://wp-archive.baka.li/2014/03/Chromium-OS-DOWN-150x79.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-DOWN-300x158.png 300w" sizes="(max-width: 791px) 100vw, 791px" />][10]

不过直接打开的话是没有网络的，没有网络的话登录不了就用不了，Chromium OS是一个云系统，没网络就废了。

用记事本编辑器打开VMX文件，在最后一行添加一行后保存；如下图。

[syntax type=&#8221;html|php|js|css&#8221;]

<pre>ethernet0.virtualDev = "e1000"</pre>

[/syntax]

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1764" src="https://wp-archive.baka.li/2014/03/Chromium-OS-VMX.png" alt="Chromium-OS-VMX" width="654" height="523" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-VMX.png 654w, https://wp-archive.baka.li/2014/03/Chromium-OS-VMX-150x119.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-VMX-300x239.png 300w" sizes="(max-width: 654px) 100vw, 654px" />][11]

然后就可以正式体验了，开机选择语言。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1765" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-37.png" alt="Chromium OS-2014-03-17-17-47-37" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-37.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-37-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-37-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-37-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][12]

自动更新，没网络连系统都进不了。

Chromium OS会自动更新，像Chrome浏览器一样，永远保持最新版本。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1766" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-48.png" alt="Chromium OS-2014-03-17-17-47-48" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-48.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-48-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-48-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-48-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][13]

登录Google帐号。

<!--more-->

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1773" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-51-11.png" alt="Chromium OS-2014-03-17-17-51-11" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-51-11.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-51-11-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-51-11-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-51-11-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][14]

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1768" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-52-04.png" alt="Chromium OS-2014-03-17-17-52-04" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-52-04.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-52-04-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-52-04-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-52-04-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][15]

设置好后二次登录的场景。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1783" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-10-52-07.jpg" alt="Chromium-OS-2014-03-18-10-52-07" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-10-52-07.jpg 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-10-52-07-150x84.jpg 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-10-52-07-300x168.jpg 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-10-52-07-1024x576.jpg 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][16]

进系统，自动同步了Chrome浏览器的书签。

不过这排列顺序出了点小问题，扩展程序也需要进设置界面同步，难道是Chrome和Chromium的接合还不够好？

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1769" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-53-45.png" alt="Chromium OS-2014-03-17-17-53-45" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-53-45.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-53-45-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-53-45-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-53-45-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][17]

右下角的菜单，有本地拼音输入法。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1762" src="https://wp-archive.baka.li/2014/03/Chromium-OS-settings.png" alt="Chromium OS-settings" width="359" height="414" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-settings.png 359w, https://wp-archive.baka.li/2014/03/Chromium-OS-settings-130x150.png 130w, https://wp-archive.baka.li/2014/03/Chromium-OS-settings-260x300.png 260w" sizes="(max-width: 359px) 100vw, 359px" />][18]

输入法界面丑啊！！！求整合Google拼音！！！

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1763" src="https://wp-archive.baka.li/2014/03/Chromium-OS-shurufa.png" alt="Chromium-OS-shurufa" width="434" height="144" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-shurufa.png 434w, https://wp-archive.baka.li/2014/03/Chromium-OS-shurufa-150x49.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-shurufa-300x99.png 300w" sizes="(max-width: 434px) 100vw, 434px" />][19]

窗口化后有类似Windows的AERO Glass的玻璃效果，可惜全屏没有。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1760" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-07-22.png" alt="Chromium OS-2014-03-18-19-07-22" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-07-22.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-07-22-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-07-22-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-07-22-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][20]

有支付宝控件，可以登录支付宝。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1774" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-11-13-37.png" alt="Chromium OS-2014-03-18-11-13-37" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-11-13-37.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-11-13-37-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-11-13-37-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-11-13-37-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][21]

还不错，可以确认收货。

网银不用想了，不过我一直用快捷支付充钱进支付宝，用Chrome OS购物是没问题了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1775" src="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-57-24.png" alt="Chromium OS-2014-03-18-19-57-24" width="1280" height="720" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-57-24.png 1280w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-57-24-150x84.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-57-24-300x168.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-57-24-1024x576.png 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][22]

Chromium OS的文件管理器，深度整合Google Drive，购买ChromeBook都会送100GB Google Drive。

自带本地音频、视频播放器，不过我播放FLAC、MP3、MP4都失败了，不解。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1776" src="https://wp-archive.baka.li/2014/03/Chromium-OS-wenjian.png" alt="Chromium OS-wenjian" width="1025" height="567" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-wenjian.png 1025w, https://wp-archive.baka.li/2014/03/Chromium-OS-wenjian-150x82.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-wenjian-300x165.png 300w, https://wp-archive.baka.li/2014/03/Chromium-OS-wenjian-1024x566.png 1024w" sizes="(max-width: 1025px) 100vw, 1025px" />][23]

还有一个重大问题就是，看不了Flash，Chrome应该整合flash的啊。

但是我想下载Flash的时候却提示ChromeBook已经内置了Flash，看来是这个编译版本有问题了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1777" src="https://wp-archive.baka.li/2014/03/Chromium-OS-flash.png" alt="Chromium OS-flash" width="583" height="242" srcset="https://wp-archive.baka.li/2014/03/Chromium-OS-flash.png 583w, https://wp-archive.baka.li/2014/03/Chromium-OS-flash-150x62.png 150w, https://wp-archive.baka.li/2014/03/Chromium-OS-flash-300x124.png 300w" sizes="(max-width: 583px) 100vw, 583px" />][24]

[divider type=&#8221;thick&#8221;]

## 总结：还是买一台ChromeBook玩玩吧！~

 [1]: https://wp-archive.baka.li/2014/03/Chromium-OS.jpg
 [2]: http://zh.wikipedia.org/wiki/Google "Google"
 [3]: http://zh.wikipedia.org/wiki/%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1 "操作系统"
 [4]: http://zh.wikipedia.org/wiki/%E4%BA%92%E8%81%94%E7%BD%91 "互联网"
 [5]: http://zh.wikipedia.org/wiki/Google_Chrome "谷歌浏览器"
 [6]: http://zh.wikipedia.org/wiki/Linux%E5%86%85%E6%A0%B8 "Linux内核"
 [7]: http://zh.wikipedia.org/wiki/Netbook "Netbook"
 [8]: http://zh.wikipedia.org/wiki/X86 "X86"
 [9]: http://zh.wikipedia.org/wiki/ARM%E6%9E%B6%E6%A7%8B "ARM架构"
 [10]: https://wp-archive.baka.li/2014/03/Chromium-OS-DOWN.png
 [11]: https://wp-archive.baka.li/2014/03/Chromium-OS-VMX.png
 [12]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-37.png
 [13]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-47-48.png
 [14]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-51-11.png
 [15]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-52-04.png
 [16]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-10-52-07.jpg
 [17]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-17-17-53-45.png
 [18]: https://wp-archive.baka.li/2014/03/Chromium-OS-settings.png
 [19]: https://wp-archive.baka.li/2014/03/Chromium-OS-shurufa.png
 [20]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-07-22.png
 [21]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-11-13-37.png
 [22]: https://wp-archive.baka.li/2014/03/Chromium-OS-2014-03-18-19-57-24.png
 [23]: https://wp-archive.baka.li/2014/03/Chromium-OS-wenjian.png
 [24]: https://wp-archive.baka.li/2014/03/Chromium-OS-flash.png