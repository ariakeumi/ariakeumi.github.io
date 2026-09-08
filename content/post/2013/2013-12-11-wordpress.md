---
title: 炒土豆丝のWordPress
author: 炒土豆丝
type: post
date: 2013-12-11T05:06:02+00:00
url: /wordpress/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 8542
dsq_thread_id:
  - 3975456301
views:
  - 3130
categories:
  - it
tags:
  - VPS
  - WordPress

---
## [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-911" src="https://wp-archive.baka.li/2013/12/WordPress.jpg" alt="WordPress" width="960" height="520" />][1]

  *  域名

原来使用的是免费的<a href="http://www.dot.tk/zh/index.html" target="_blank" rel="noopener">TK域名</a>，免费的始终是免费的，只能用来玩玩。

2013 年 12 月 10 日在 <a href="http://www.godaddy.com/" target="_blank" rel="noopener">Godadyy</a> 上注册了 Bakatd.com 这个域名。

2015 年 6 月转移到新域名 bakahouse.com ，刚过一个月，觉得这域名太长又注册了 bakayo.com 。这是我用得最长的域名，使用了将近三年。

2018 年 3 月，因为抢注 bakawu.com 这个域名失败，决定放弃使用 .com 的顶级域名。并在当月注册 umi.im 这个国别域名。

  * ## 主机

2013 年的时候我用的是 <a href="http://www.kilu.de/" target="_blank" rel="noopener">Kilu</a> 的免费空间，10GB无限流量，速度一般，没有伪静态不能固定链接。本来打算一直用下去，后来有人愿意给我提供 <a href="http://blog.wpjam.com/article/media-temple/" target="_blank" rel="noopener">Media Temple主机</a> 。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-617" src="https://wp-archive.baka.li/2013/12/QQJieTu20131210194451.png" alt="QQ截图20131210194451" width="389" height="173" />][2]

在准备搬家到MT时，屋主所在的20号服务器宕机了。

2014 年初，MT主机提供者迁移到阿里云主机。同年二月被迫搬家到了<a href="https://baka.li/2014-web-hosting/" target="_blank" rel="noopener">老薛主机</a>，价格便宜，流量美国主机+ 1G空间附加包不到100元。

2015 年 6 月，朋友购买 <a href="https://baka.li/vps-ubuntu-wordpress/" target="_blank" rel="noopener">DigitalOcean VPS</a> 搭建 <a title="DigitalOcean VPS 安装 Shadowsocks" href="https://baka.li/digitalocean-vps-shadowsocks/" target="_blank" rel="noopener">Shadowsocks</a> 代理，我顺便搬了过去。

2015 年 8 月 25 日，搬到了 BudgetVM 的廉价 VPS 上。

2017 年，为了看 Twitch 搭建 Shadowsocks 翻墙购下了 CN2 线路的 [搬瓦工 VPS][3] ，博客也顺便搬了过去，速度不错价格便宜，打算常驻。

  * ## 主题

## <a href="http://www.tystudio.net/2013/09/07/bliss-wordpress-theme/#more-1009" target="_blank" rel="noopener">WordPress博客主题Bliss深度汉化分享</a>

本站使用的是由<a href="http://weibo.com/signup/signup.php?inviteCode=3152350884" target="_blank" rel="noopener">天屹</a>汉化的<a href="http://themeforest.net/item/bliss-personal-minimalist-wordpress-blog-theme/5423780" target="_blank" rel="noopener">Bliss主题</a>，功能方面非常强大。

主题里面还有两个插件，需要自行安装。

  * ## 插件

## <a href="http://blog.wpjam.com/article/google-xml-sitemaps/" target="_blank" rel="noopener">Google XML Sitemaps</a>

WordPress必备插件，自动生成网站地图，方便搜索引擎抓取提高排名。

## <del><a href="http://wordpress.org/plugins/duoshuo/" target="_blank" rel="noopener">多说社会化评论框</a></del>

<del>可以用QQ，微博甚至G+帐号登录评论，在其他安装了多说的网站登录后就可以在任何有多说插件的网站里留言而不必再次登录。</del>

<del>而且竟然有我非常喜欢的喜悠候和柏夫的表情。</del>

<del>缺点也很明显，部分用户可能很难看到提醒。</del>

## <a href="http://www.brunoxu.com/useso-take-over-google.html" target="_blank" rel="noopener">Crayon Syntax Highlighter</a>

代码高亮插件。

## <a href="https://wordpress.org/plugins/si-captcha-for-wordpress/" target="_blank" rel="noopener">SI Captcha Anti-Spam</a>

给用户注册、登录和回复添加验证码，有效防止垃圾评论。

## <a href="http://wordpress.org/plugins/comment-reply-notification/" target="_blank" rel="noopener">Comment Reply Notification</a>

WordPress必备插件，回复别人的留言时能自动发送邮件给留言者，如果用了多说就不需要它了。

## <a href="http://pan.baidu.com/share/link?shareid=2161015992&uk=3191095378" target="_blank" rel="noopener">Show-Useragent</a>

在评论里面显示评论者的国籍，浏览器，操作系统的信息。

传了修改版的，原版暂时还没法识别WIN8.1。

## <a href="http://ihacklog.com/post/hacklog-downloadmanager.html" target="_blank" rel="noopener">Hacklog-DownloadManager</a>

下载管理插件，WordPress默认是不允许上传种子文件的，有了它就可以上传种子还可以统计下载信息设置下载权限等。我在另一个网站里有用到。

## <a href="http://wordpress.org/support/plugin/backwpup" target="_blank" rel="noopener">BackWPup</a>

功能超级强大的备份插件，支持自动备份到邮箱和<a href="http://dropbox.com/" target="_blank" rel="noopener">DropBox</a>，能把网站网站备份。

&nbsp;

## <a href="http://wordpress.org/plugins/google-search-cse/" target="_blank" rel="noopener">WordPress Google Search</a>

谷歌自定义搜索插件，WordPress自带的搜索不仅占用服务器资源而且不够精准。

在<a href="http://www.google.com/cse/?hl=zh-CN" target="_blank" rel="noopener">谷歌自定义搜索</a>中注册自己网站，然后固定小工具位置，不需要设置就可使用。

## <a href="http://wordpress.org/plugins/all-in-one-seo-pack/" target="_blank" rel="noopener">All In One SEO Pack</a>

著名的SEO插件。

## <a href="https://wordpress.org/plugins/hermit/" target="_blank" rel="noopener">Hermit</a>

在文章中嵌入虾米音乐。

  * 服务

## <a href="http://blog.wpjam.com/project/wpjam-qiniutek/" target="_blank" rel="noopener">七牛云储存</a>

把静态文件放在七牛云空间上实现CDN加速。免费帐号有10BG空间，每月也10GB流量，够大多数人用了。

## <del><a href="http://www.freehao123.com/cloudflare-cdn/" target="_blank" rel="noopener">CloudFlare</a></del>

<del>免费的CDN加速服务，屋主在用Kilu空间时使用，效果不错，使用起来也很简单。</del>

 [1]: https://wp-archive.baka.li/2013/12/WordPress.jpg
 [2]: https://wp-archive.baka.li/2013/12/QQJieTu20131210194451.png
 [3]: https://baka.li/bandwagon/