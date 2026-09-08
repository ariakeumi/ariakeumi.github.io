---
title: Carbon Forum 轻型 PHP 论坛搭建
author: 炒土豆丝
type: post
date: 2015-07-23T12:24:07+00:00
url: /carbon-forum/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 6719
dsq_thread_id:
  - 3975411222
views:
  - 1134
categories:
  - it
tags:
  - VPS

---
平时非常喜欢论坛，一直有建个论坛玩玩的想法。像 Discuz 这种论坛程序 VPS 肯定是玩不转的，而且也用不上那么多功能。

最近迷上了 V2EX 这个轻型论坛，基于话题而非版块的划分太适合小论坛。

然后我发现自己关注的知乎用户 <a href="http://www.zhihu.com/people/lincanbin" data-tip="p$b$lincanbin">林灿斌</a> 竟然有一个轻型的开源论坛项目，轻到能在5美元一个月的 VPS上跑，这说的不就是 <a title="炒土豆丝的 WordPress 新家：VPS ~ Ubuntu + Apache + MySQL + PHP" href="https://baka.li/vps-ubuntu-wordpress/" target="_blank">DigitalOcean</a> 的 VPS 么！建站时机已到！

## <a class=" wrap external" href="https://github.com/lincanbin/Carbon-Forum" target="_blank" rel="nofollow noreferrer">lincanbin/Carbon-Forum · GitHub<i class="icon-external"></i></a>

> Carbon Forum，一个高性能的、高安全性的、基于话题的PHP轻论坛。
> 
> 优秀的架构，高效的代码，每个页面平均执行时间仅为1~5毫秒，同时恰当地使用异步加载技术，在SEO与用户体验间取得平衡。
> 
> 论坛摒弃了版块、节点等概念，发帖时无需选择板块，系统根据帖子内容自动推荐话题供用户选择，并且有功能强大而不显冗余的富文本编辑器。
> 
> 支持关注用户、关注话题等功能，可以作为一个社交网站使用。

Carbon Forum 安装起来很简单，甚至比 WordPress 还简单，但是安装过程中遇到的几个问题麻烦了半天，一步一步记下来。

## Ubuntu + Apache2 Virtual Host 配置

我希望通过子域名 bbs.*.com 来实现论坛的访问，主域名留给博客，这时候就需要设置 Virtual Host 。

搭建 Carbon Forum 除了用到 bbs 子域名，还可以设置一个移动版域名，所以要设置3个 Virtual Host 。

在 /etc/apache2/sites-available/ 目录下有一个 default.conf 的配置文件，复制文件命名为要设定的域名，配置3个。

  * umi.im.conf
  * bbs.umi.im.conf
  * m.umi.im.conf

以上3个分别为 WordPress 博客域名，Carbon 论坛域名，Carbon 论坛移动版域名。

<pre class="lang:default decode:true">#
# DocumentRoot 是网站文件存放的根目录,论坛移动版域名也设定为 Carbon 文件存放目录
# ServerName 是网站域名
#
&lt;VirtualHost *:80&gt;
    ServerAdmin webmaster@dummy-host.example.com
    DocumentRoot /var/www/html/bbs
    ServerName bbs.umi.im
    ErrorLog ${APACHE_LOG_DIR}/bbs.bakahouse.com-error.log
    CustomLog ${APACHE_LOG_DIR}/bbs.bakahouse.com-access.log combined
&lt;/VirtualHost&gt;</pre>

接着通过 a2ensite 激活 Virtual Host 配置，再重启 Apache2 。

<pre class="lang:default decode:true"># a2ensite umi.im
# a2ensite bbs.umi.im
# a2ensite m.umi.im
# service apache2 restart</pre>

我的论坛 Virtual Host 路径是 /var/www/html/bbs ，把扔到对应的路径上就好了。

## 开启伪静态

开启Apache2 伪静态 rewrite 支持，这一步出问题可能导致接下来安装完成后页面 404 。

<pre class="lang:default decode:true"># a2enmod rewrite</pre>

然后修改  /etc/apache2/apache2.conf ，把 AllowOverride None 改为 AllowOverride All ，可能有4行。

## 安装

先登录 phpmyadmin 添加个数据库，名字随意。

打开域名 bbs.umi.im/install 开始安装，输入数据库名字、数据库账号密码就安装完成，然后手动删除 install 和 update 目录。

另外还要给目录 777 权限，用 FTP 软件 FlashFXP 或者 Winscp都可以很简单的设置。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4396" src="https://wp-archive.baka.li/2015/07/Carbon-Forum-777.png" alt="Carbon Forum  777" width="479" height="406" srcset="https://wp-archive.baka.li/2015/07/Carbon-Forum-777.png 479w, https://wp-archive.baka.li/2015/07/Carbon-Forum-777-150x127.png 150w, https://wp-archive.baka.li/2015/07/Carbon-Forum-777-300x254.png 300w" sizes="(max-width: 479px) 100vw, 479px" />][1]

## <a href="http://bbs.umi.im/" target="_blank">BAKA里屋 | 就我一个用户</a>

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4401" src="https://wp-archive.baka.li/2015/07/MacBook-Pro-Carbon-Forum.jpg" alt="MacBook Pro Carbon Forum" width="1280" height="853" srcset="https://wp-archive.baka.li/2015/07/MacBook-Pro-Carbon-Forum.jpg 1280w, https://wp-archive.baka.li/2015/07/MacBook-Pro-Carbon-Forum-150x100.jpg 150w, https://wp-archive.baka.li/2015/07/MacBook-Pro-Carbon-Forum-300x200.jpg 300w, https://wp-archive.baka.li/2015/07/MacBook-Pro-Carbon-Forum-1024x682.jpg 1024w" sizes="(max-width: 1280px) 100vw, 1280px" />][2]

 [1]: https://wp-archive.baka.li/2015/07/Carbon-Forum-777.png
 [2]: https://wp-archive.baka.li/2015/07/MacBook-Pro-Carbon-Forum.jpg