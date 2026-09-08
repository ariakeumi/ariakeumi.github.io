---
title: 漂亮的 Ubuntu 主题 Flatabulous
author: 炒土豆丝
type: post
date: 2015-09-25T01:43:22+00:00
url: /ubuntu-theme-flatabulous/
featured_image: https://wp-archive.baka.li/2015/09/ubuntu-theme-flatabulous.jpg
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 2173
dsq_thread_id:
  - 4164425364
views:
  - 780
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - app
tags:
  - Linux
  - Ubuntu

---
昨天给 ChromeBook Pixel 安装了 Ubuntu 14.04 ，用&nbsp;<a href="https://github.com/dnschneid/crouton" target="_blank" rel="noopener">Crouton</a>&nbsp;安装，可以实时切换回 Chrome OS，<a href="http://www.encrhome.com/?p=2781" target="_blank" rel="noopener">安装方法</a>。

Ubuntu 的 Unity 桌面我一直很喜欢，特别是 Dock 位于屏幕左侧的设计。所以顺便分享个 Unity 的漂亮主题，暗色风格的&nbsp;OS X Yosemite？

[<img loading="lazy" decoding="async" width="998" height="663" src="https://wp-archive.baka.li/2015/09/ubuntu-theme-flatabulous.jpg" alt="ubuntu-theme-flatabulous" class="wp-image-4633" srcset="https://wp-archive.baka.li/2015/09/ubuntu-theme-flatabulous.jpg 998w, https://wp-archive.baka.li/2015/09/ubuntu-theme-flatabulous-150x100.jpg 150w, https://wp-archive.baka.li/2015/09/ubuntu-theme-flatabulous-300x199.jpg 300w" sizes="(max-width: 998px) 100vw, 998px" />][1] 

Ubuntu 安装主题非常简单，首先安装 <a href="http://ubuntu-tweak.com/" target="_blank" rel="noopener">Ubuntu Tweak</a> ，到官网下载 Deb 包双击打开就可以安装。

或者用 apt-get 命令安装：

<pre class="wp-block-code"><code>sudo add-apt-repository ppa:tualatrix/ppa  
sudo apt-get update  
sudo apt-get install ubuntu-tweak</code></pre>

然后下载&nbsp;<a href="https://github.com/anmoljagetia/Flatabulous/archive/master.zip" target="_blank" rel="noopener">Flatabulous 主题</a>&nbsp;，点击下载。

下载完成后打开终端，移动到下载目录解压文件顺便把主题移动到系统的主题目录，输入如下命令：

<pre class="wp-block-code"><code>cd Downloads/
unzip Flatabulous-master.zip
sudo cp -a Flatabulous-master /usr/share/themes/</code></pre>

最后打开&nbsp; Ubuntu Tweak ，在 Tweaks &#8211; Theme &#8211; Gtk theme 项选择 &nbsp;Flatabulous-master 就完成了。

[<img loading="lazy" decoding="async" width="560" height="334" src="https://wp-archive.baka.li/2015/09/Ubuntu-tweak-tool.jpg" alt="Ubuntu tweak tool" class="wp-image-4634" srcset="https://wp-archive.baka.li/2015/09/Ubuntu-tweak-tool.jpg 560w, https://wp-archive.baka.li/2015/09/Ubuntu-tweak-tool-150x89.jpg 150w, https://wp-archive.baka.li/2015/09/Ubuntu-tweak-tool-300x179.jpg 300w" sizes="(max-width: 560px) 100vw, 560px" />][2] 

作者还分享了个扁平化的图标包，不过我不太喜欢就不转来了，详情访问作者博客。

## <a href="https://blog.anmoljagetia.me/flatabulous-ubuntu-theme/" target="_blank" rel="noopener">Flatabulous : Ubuntu Theme /&nbsp;Anmol Jagetia&#8217;s Blog!</a> 

 [1]: https://wp-archive.baka.li/2015/09/ubuntu-theme-flatabulous.jpg
 [2]: https://wp-archive.baka.li/2015/09/Ubuntu-tweak-tool.jpg