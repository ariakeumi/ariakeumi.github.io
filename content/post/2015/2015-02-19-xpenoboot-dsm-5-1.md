---
title: XPEnoboot DSM 5.1-5022.2 黑群晖升级安装
author: 炒土豆丝
type: post
date: 2015-02-18T16:42:18+00:00
url: /xpenoboot-dsm-5-1/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 9222
dsq_thread_id:
  - 3982643411
views:
  - 900
categories:
  - it
tags:
  - NAS
  - 黑群晖

---
群晖的NAS系统DSM 5.1终于被破解了，由原来的Nanoboot开发者发布。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3505" src="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1.png" alt="xpenoboot-dsm-5-1" width="841" height="547" srcset="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1.png 841w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-150x98.png 150w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-300x195.png 300w" sizes="(max-width: 841px) 100vw, 841px" />][1]

保留文件升级方法和DSM 4.2升级DSM 5.0一样，很简单，下载XPEnoboot的引导镜像（img格式）和群晖 DS3615xs的官方PAT安装文件。

## <a href="http://nanoboot.eu.org/download" target="_blank">XPEnoboot 引导镜像 下载</a>

## <a href="https://www.synology.com/zh-cn/support/download/DS3615xs" target="_blank">DS3615xs 安装文件 下载</a>

用Win32 Disk Imager把XPEnoboot的引导镜像写入U盘。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3506" src="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-2.png" alt="xpenoboot-dsm-5-1-2" width="421" height="214" srcset="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-2.png 421w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-2-150x76.png 150w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-2-300x152.png 300w" sizes="(max-width: 421px) 100vw, 421px" />][2]

然后BIOS设置U盘启动，选择 DSM 5.1(install/upgrade) ，然后在浏览器打开DSM的Web页面，或者用群晖助手辅助，

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3507" src="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-3.png" alt="xpenoboot-dsm-5-1-3" width="1363" height="936" srcset="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-3.png 1363w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-3-150x103.png 150w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-3-300x206.png 300w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-3-1024x703.png 1024w" sizes="(max-width: 1363px) 100vw, 1363px" />][3]

选择刚才下载的DS3615xs 安装文件。[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3508" src="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-4.png" alt="xpenoboot-dsm-5-1-4" width="1363" height="936" srcset="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-4.png 1363w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-4-150x103.png 150w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-4-300x206.png 300w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-4-1024x703.png 1024w" sizes="(max-width: 1363px) 100vw, 1363px" />][4] [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3509" src="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-5.png" alt="xpenoboot-dsm-5-1-5" width="1363" height="936" srcset="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-5.png 1363w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-5-150x103.png 150w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-5-300x206.png 300w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-5-1024x703.png 1024w" sizes="(max-width: 1363px) 100vw, 1363px" />][5] [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3510" src="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-6.png" alt="xpenoboot-dsm-5-1-6" width="1363" height="936" srcset="https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-6.png 1363w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-6-150x103.png 150w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-6-300x206.png 300w, https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-6-1024x703.png 1024w" sizes="(max-width: 1363px) 100vw, 1363px" />][6]

安装完成自动重启，然后就OK了。

相对于DSM 4.2到DSM 5.0，DSM 5.1只能算是很小的更新。

主要多了Note Station功能，一个私有云笔记，和Evernote相比没什么优势，甚至可能还没有Evernote安全。

## <a href="https://www.synology.com/zh-cn/dsm/5.1" target="_blank">DiskStation Manager 5.1</a>

 [1]: https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1.png
 [2]: https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-2.png
 [3]: https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-3.png
 [4]: https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-4.png
 [5]: https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-5.png
 [6]: https://wp-archive.baka.li/2015/02/xpenoboot-dsm-5-1-6.png