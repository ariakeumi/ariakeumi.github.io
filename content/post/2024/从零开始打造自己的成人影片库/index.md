---

title: "在线编程平台（IDE）"

description: ""

date: 2024-01-02

image: wordpress-to-hugo.webp

draft: true

categories: ["it","app"]

tags: ["博客"]

url: /av-test/

---



# 从零开始打造自己的成人影片库

### 前言

博客建立十多年了，因为技术水平太菜没写过什么干货文章，唯独几篇开车内容的点击量遥遥领先。最近几年也没更过这方面的内容了，遂决定写一篇下载 AV 到刮削并建立影片库的教程。

本文门槛很低，不需要 NAS 、命令行工具等，可能需要科学上网。



### 找片

-  [PlayNo1](http://www.playno1.com/portal.php?mod=list&catid=78) ，号称華人最大成人新聞情報站 ，站长 [一劍浣春秋](https://zh.wikipedia.org/wiki/%E4%B8%80%E5%8A%8D%E6%B5%A3%E6%98%A5%E7%A7%8B) 是专门研究日本 AV 的专家，获取新片新人女优资讯很靠谱，此网站很神奇的没有被中国大陆屏蔽。
- [老司機論壇](https://www.javbus.com/forum/) ，JAVBUS 网站的论坛，全是人才，站内的 [求福利帶帶我](https://www.javbus.com/forum/forum.php?mod=forumdisplay&fid=36) 分区更是鉴黄高手聚集地，建议先注册个账号混点分方便以后求种。

- [JAV金鸡儿奖](https://jinjier.art/) ，JAV 金鸡儿奖是在中国电影金鸡奖的影响下，由中国AV影评人协会(CACA)发起，并与国际AV研究顶会AAAA联合主办的奖项，是JAV领域最权威、最专业的奖项，代表着JAV领域的最高荣誉。
- [Javlibrary](https://www.javlibrary.com/cn/vl_bestrated.php) 评价最高的影片 ，专业榜单，口味偏中年男性。

- [JAVDB TOP250](https://javdb.com/rankings/top) ，大众口味榜单，需要充值会员才能查看。

### 下载

这个没什么好说的，磁力链接直接用迅雷下载就行，热门资源速度反而比 qBittorrent 等专业下载器快。

###  刮削

刮削指的是从互联网上抓取 AV 的封面图片和包含影片简介、演员、发行日期等信息的元数据，帮助媒体库索引 AV 。

[MDCx](https://github.com/sqzw-x/mdcx/releases/tag/120240321) 是我用过最好的带图形界面的刮削器，它不仅可以帮你刮削 AV 封面和元数据，还可以通过翻译 API 等方法刮削到影片的中文名称，亦或是给封面加上 **破解** 、 **流出** 等字样的水印。



### 媒体库

刮削整理完影片后就开始选择一种优雅的方法来打开影片了。

这次我抛弃 Jellyfin 和 EMBY 之类的 NAS 媒体库软件，直接使用 ALEX 来