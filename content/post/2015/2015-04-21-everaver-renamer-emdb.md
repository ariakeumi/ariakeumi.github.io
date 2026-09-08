---
title: '科学的管理AV  ~  EverAver Renamer + EMDB 建立自己的AV媒体库'
author: 炒土豆丝
type: post
date: 2015-04-21T12:25:12+00:00
url: /everaver-renamer-emdb/
wpb_post_views_count:
  - 46090
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
dsq_thread_id:
  - 3975481154
views:
  - 3279
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - xxx
tags:
  - AV
  - Hentai
  - Windows 软件

---
<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    <strong><span style="color: #ff0000;">WARNING：If you are under 18 years of age, or if it is illegal to view adult material in your community, please leave now.</span></strong>
  </p>
</blockquote>

本文主要介绍利用&nbsp;EverAver Renamer 整理本地AV并获取AV封面，然后用EMDB生成媒体库，便于以后更快的找到想看的AV，或者只是满足整理控的需求。

EverAver Renamer 能抓取AV片商官网的AV信息为本地AV影片重命名并进行分类，EverAver Renamer 需要全局翻墙才能使用，这里就不详细介绍如何翻墙了。

骑兵模式（有码AV）：

因为是通过番号搜索AV片商网站上的信息进行匹配的，所以影片名字中必须包含番号、

番号一般是字母+数字的格式，如果提示 “查无此片” ，请检查番号是否正确，或者去掉搜索框多余字符只保留番号。

步兵模式（无码AV）：

无码片大都是一本道、东京热、加勒比等在线付费下载网站的，并没有实体渠道，所以也没有商品番号这种东西（有编号，来自网站Url），DVD封面自然也没有。

所以只有少量带番号的无码AV可以找到封面。

<img loading="lazy" decoding="async" width="800" height="631" src="https://wp-archive.baka.li/2022/11/EverAver-Renamer-1-x.png" alt="" class="wp-image-6232" />  

目录结构：

<pre class="wp-block-preformatted">%actor%\%maker%</pre>

默认目录结构是 “AV女优名字\AV片商名字 ”，如果收藏的某AV女优的片子比较多，建议建立单级AV女优目录，出品公司这个没什么必要分类，除非要以AV片商名字分类有码无码。

<pre class="wp-block-preformatted">%actor%</pre>

命名格式：

<pre class="wp-block-preformatted">%actor% - [%maker%] %title% [%num%]</pre>

默认命名格式是 “AV女优名字 &#8211; AV片商名字&nbsp;&#8211; AV片名 [番号]” ，如果以建立了AV女优目录进行分类，那么命名中的女优名字就可以去掉，片名标题末端一般都会补上名字，AV片商名字这种不太重要的可以放到最后面，番号的话个人建议放前面，另外最好不要建立同名目录，这样找片不方便。

<pre class="wp-block-preformatted">%num% - %title% [%maker%]</pre>

[<img loading="lazy" decoding="async" width="400" height="501" src="https://wp-archive.baka.li/2015/01/EverAver-Renamer-2.png" alt="EverAver Renamer-2" class="wp-image-3722" srcset="https://wp-archive.baka.li/2015/01/EverAver-Renamer-2.png 400w, https://wp-archive.baka.li/2015/01/EverAver-Renamer-2-120x150.png 120w, https://wp-archive.baka.li/2015/01/EverAver-Renamer-2-240x300.png 240w" sizes="(max-width: 400px) 100vw, 400px" />][1] 

整理完成后，打开EMDB菜单栏的“硬盘”项，将存放AV的文件夹加入数据库即可。

[<img loading="lazy" decoding="async" width="776" height="554" src="https://wp-archive.baka.li/2015/01/EMDB-HDD.png" alt="EMDB-HDD" class="wp-image-3723" srcset="https://wp-archive.baka.li/2015/01/EMDB-HDD.png 776w, https://wp-archive.baka.li/2015/01/EMDB-HDD-150x107.png 150w, https://wp-archive.baka.li/2015/01/EMDB-HDD-300x214.png 300w" sizes="(max-width: 776px) 100vw, 776px" />][2] 

在菜单栏“选项”里设定回车或双击播放视频。

[<img loading="lazy" decoding="async" width="850" height="618" src="https://wp-archive.baka.li/2015/01/EMDB-ST.png" alt="EMDB-ST" class="wp-image-3724" srcset="https://wp-archive.baka.li/2015/01/EMDB-ST.png 850w, https://wp-archive.baka.li/2015/01/EMDB-ST-150x109.png 150w, https://wp-archive.baka.li/2015/01/EMDB-ST-300x218.png 300w" sizes="(max-width: 850px) 100vw, 850px" />][3] 

最终效果。

<img loading="lazy" decoding="async" width="1283" height="821" src="https://wp-archive.baka.li/2022/11/av-emdb-x.jpg" alt="" class="wp-image-6233" />  

我的AV是放在<a href="https://baka.li/nas-synology/" target="_blank" rel="noopener">黑群晖NAS</a>上的，通过iPad的DS Video访问效果更好，因为没有封面的无码AV会自动生成预览图。

<img loading="lazy" decoding="async" width="1280" height="960" src="https://wp-archive.baka.li/2022/11/DS-VIDEO-AV-x.jpg" alt="" class="wp-image-6234" />  

下载地址：

##  <a href="http://pan.baidu.com/s/1o6p7p2a" target="_blank" rel="noopener">EverAver Renamer</a>（百度云） 

## <a href="http://www.emdb.eu/software.htm" target="_blank" rel="noopener">EMDB</a>（官方） 

开发者网站：

## <a href="http://www.emdb.eu/index.htm" target="_blank" rel="noopener">EverAver&nbsp;獻給每一位偉大的AVer…</a> 

##  <a href="http://www.emdb.eu/index.htm" target="_blank" rel="noopener">emdb.eu<br /></a> 

 [1]: https://wp-archive.baka.li/2015/01/EverAver-Renamer-2.png
 [2]: https://wp-archive.baka.li/2015/01/EMDB-HDD.png
 [3]: https://wp-archive.baka.li/2015/01/EMDB-ST.png