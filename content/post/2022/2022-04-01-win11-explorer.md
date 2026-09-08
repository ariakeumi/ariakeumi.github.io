---
title: 给 Windows 11 22H2 的资源管理器加上多标签页功能
author: 炒土豆丝
type: post
date: 2022-03-31T19:22:17+00:00
url: /win11-explorer/
featured_image: https://wp-archive.baka.li/2022/04/win11-explorer.png
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 1454
categories:
  - it
tags:
  - Windows

---
 

时隔多年，微软终于再次给 Windows 的资源管理器加上多标签页，最新的 Win11 DEV 预览版 22H2 Build 22581 隐藏了这项功能，开启很简单。

<div class="wp-block-argon-github github-info-card card shadow-sm github-info-card-full" data-author="thebookisclosed" data-project="vive">
  <div class="github-info-card-header">
    <a href="https://github.com/" target="_blank" title="Github" rel="noopener"><span><i class="fa fa-github"></i> GitHub</span></a>
  </div>
  
  <div class="github-info-card-body">
    <div class="github-info-card-name-a">
      <a href="https://github.com/thebookisclosed/vive" target="_blank" rel="noopener"><span class="github-info-card-name">thebookisclosed/vive</span></a>
    </div>
    
    <div class="github-info-card-description">
    </div>
  </div>
  
  <div class="github-info-card-bottom">
    <span class="github-info-card-meta github-info-card-meta-stars"><i class="fa fa-star"></i> <span class="github-info-card-stars"></span></span><span class="github-info-card-meta github-info-card-meta-forks"><i class="fa fa-code-fork"></i> <span class="github-info-card-forks"></span></span>
  </div>
</div>

在 Github 下载 [ViveTool][1] 工具，解压，在软件目录右键选择 ”在终端中打开“ ，然后在命令行输入下面的命令重启就行。

<pre class="wp-block-code"><code>#开启文件资源管理器标签页功能
.\vivetool addconfig 34370472 2
#删除文件资源管理器标签页功能
.\vivetool delconfig 34370472 2
#操作完成必须重启系统才能生效</code></pre>

<img loading="lazy" decoding="async" width="905" height="616" src="https://wp-archive.baka.li/2022/04/vivetool-addconfig.png" alt="" class="wp-image-6114" />  

多标签页的快捷键基本和 Chrome 一样， Ctrl + T 新建标签页，Ctrl + W 关闭标签页，Ctrl + N 在新窗口打开资源管理器，Ctrl + Tab 和 Ctrl + Shift + Tab 是左右切换标签页。

<img loading="lazy" decoding="async" width="1116" height="823" src="https://wp-archive.baka.li/2022/04/win11-explorer.png" alt="" class="wp-image-6112" />  

说起来在很早以前，我通过一个叫 <a rel="noreferrer noopener" href="http://cn.ejie.me/" target="_blank">Clover</a> 的软件在资源管理器加上类似 Chrome 的多标签页功能，不过好景不长，软件的开发者把项目卖掉了，然后 Clover 就越来越难用了，在 Win10 上经常卡死，不得不回到打开一堆资源管理器窗口的日子，然后也尝试了 QTTabBar 这种类似的软件，但还是不习惯用。

希望这功能不要微软被砍掉&#8230;

 [1]: https://github.com/thebookisclosed/ViVe/releases/tag/v0.2.1