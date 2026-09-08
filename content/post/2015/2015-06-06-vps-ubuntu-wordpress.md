---
title: 炒土豆丝的 WordPress 新家：VPS ~ Ubuntu + Apache + MySQL + PHP
author: 炒土豆丝
type: post
date: 2015-06-06T12:10:54+00:00
url: /vps-ubuntu-wordpress/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 2928
duoshuo_thread_id:
  - 1278228446777966893
dsq_thread_id:
  - 3975480401
views:
  - 696
categories:
  - it
tags:
  - Linux
  - VPS
  - WordPress
  - 域名

---
接上文，拿到 <a href="http://bbs.colg.cn/home.php?mod=space&uid=601303" target="_blank">@茄子泥焗黃魚</a> 土豪的 VPS 后&#8230;

折腾好 Shadowsocks 服务端，就打算把网站搬到 VPS 上，之前的<a href="https://baka.li/2014-web-hosting/" target="_blank">虚拟主机</a>虽然便宜，但速度真的不怎么样，偶尔还会抽风。像我这种日访问量在个位数的网站，搬到这种配置的 VPS 上应该会很爽。

既然要搬家，那就顺便换个域名吧。

原域名 <a href="http://bakatd.com/" target="_blank">bakatd.com</a> ，虽然简短，但是不能通读，所以换成了现在的 <a href="https://baka.li/" target="_blank">bakahouse.com</a> ，读音：巴卡豪斯&#8230;意译：笨蛋公寓，参考了白宫的域名 <a href="https://www.whitehouse.gov/" target="_blank">whitehouse.gov</a> 。

先设置把旧域名转发到新域名。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3969" src="https://wp-archive.baka.li/2015/06/godaddy-Forwarding.png" alt="godaddy-Forwarding" width="533" height="278" srcset="https://wp-archive.baka.li/2015/06/godaddy-Forwarding.png 533w, https://wp-archive.baka.li/2015/06/godaddy-Forwarding-150x78.png 150w, https://wp-archive.baka.li/2015/06/godaddy-Forwarding-300x156.png 300w" sizes="(max-width: 533px) 100vw, 533px" />][1]

## <a href="http://wiki.ubuntu.org.cn/Vps" target="_blank">Linux VPS Ubuntu 系统配置指南</a>

VPS 的 Web 环境选择，Ubuntu 的中文 WIKI 写得最详细，所以我选择了 Ubuntu&#8230;

使用 Apache 搭建站点，对着 WIKI 上的命令一直复制粘贴，返回结果结果都正常，很方便的就配置好了 Apache + MySQL + PHP 。

但是测试站点的时候死活打不开，折腾着终于发现我配置的 Web 根目录是 /var/www/html ，而不是 WIKI 上写的 /var/www/ 目录，把文件移动到 /var/www/html 目录后终于能打开测试站点了。

测试站点：<a href="http://www.yahei.net/" target="_blank">雅黑PHP探针</a>

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3964" src="https://wp-archive.baka.li/2015/06/tz-php.png" alt="tz-php" width="927" height="455" srcset="https://wp-archive.baka.li/2015/06/tz-php.png 927w, https://wp-archive.baka.li/2015/06/tz-php-150x74.png 150w, https://wp-archive.baka.li/2015/06/tz-php-300x147.png 300w" sizes="(max-width: 927px) 100vw, 927px" />][2]

测试完成，Phpmyadmin 也安装完成后，就可以给网站搬家了。

我的 WordPress 网站文件备份在 Dropbox ，通过 Dropbox 分享链接，然后用 wget 命令下载。

<pre class="lang:default decode:true ">wget http://***.com/**/backwpup_bfbdbe_2015-06-05_10-08-58.tar.gz?dl=0</pre>

下载后把文件重命名为 tar.gz 格式后辍，再移动到 Web 根目录，解压：

<pre class="lang:default decode:true">tar zxvf backwpup_bfbdbe_2015-06-05_10-08-58.tar.gz</pre>

接着修改 WP-Config 配置文件，把数据库名称、账号、密码等改成现在的 VPS 的。

再进入 Phpmyadmin 导入以前的 SQL 数据库备份。

因为这次不仅搬主机，还顺便换了下域名，所以 SQL 数据库也需要把老域名改为新域名，执行几句简单的语句就好了。

## <a href="http://www.dimshadow.com/blog/program-advanced/wp/wordpress-%E6%90%AC%E5%AE%B6%E6%8D%A2%E5%9F%9F%E5%90%8D%E6%97%B6sql%E9%9C%80%E8%A6%81%E5%81%9A%E7%9A%84%E4%BF%AE%E6%94%B9.html" target="_blank">wordpress 搬家换域名时SQL需要做的修改</a>

正以为大功告成准备休息时，却发现除了主页和后台，其他链接打开都是404。

## <a href="http://www.wpdaxue.com/wordpress-rewriterule.html" target="_blank">WordPress 伪静态规则（IIS/Apache/Nginx）</a>

查了下资料说是伪静态问题，在站点根目录建一个 .htaccess 文件，复制如下代码保存：

<pre class="lang:default decode:true ">&lt;IfModule mod_rewrite.c&gt;
RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
&lt;/IfModule&gt;

</pre>

发现还是不行，再用 vi 编辑器修改下 apache2.conf 配置。

<pre class="lang:default decode:true ">vi /etc/apache2/apache2.conf</pre>

找到

<pre class="lang:default decode:true ">Options FollowSymLinks

AllowOverride None</pre>

改为

<pre class="lang:default decode:true ">Options FollowSymLinks

AllowOverride All</pre>

保存并退出，重启 Apache2 。

<pre class="lang:default decode:true ">service apache2 restart</pre>

这次真的就大功告成了，遇到以上几个小问题，多搜索下就能找到解决办法了，至于到底哪个地方出错导致的问题我也不清楚，不管了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3962" src="https://wp-archive.baka.li/2015/06/index-photo.jpg" alt="index-photo" width="440" height="473" />][3]

 [1]: https://wp-archive.baka.li/2015/06/godaddy-Forwarding.png
 [2]: https://wp-archive.baka.li/2015/06/tz-php.png
 [3]: https://wp-archive.baka.li/2015/06/index-photo.jpg