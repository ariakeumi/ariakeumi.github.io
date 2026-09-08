---
title: Apache + WordPress 部署 SSL 加密
author: 炒土豆丝
type: post
date: 2015-06-23T02:11:31+00:00
url: /apache-wordpress-ssl/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 3091
dsq_thread_id:
  - 3975480431
views:
  - 695
categories:
  - it
tags:
  - VPS
  - WordPress

---
> **传输层安全协议**（<span class="LangWithName">英语：<span lang="en" xml:lang="en">Transport Layer Security</span></span>，缩写为 TLS），及其前身**安全套接层**（<span lang="en" xml:lang="en">Secure Sockets Layer</span>，SSL）是一种[安全协议][1]，目的是为互联网通信，提供安全及数据完整性保障。在[网景][2]公司（<span lang="en" xml:lang="en">Netscape</span>）推出首版Web浏览器的同时提出SSL，[IETF][3]{.mw-redirect}将SSL进行标准化，1999年公布了 TLS标准文件。
> 
> <p style="text-align: left;">
>   SSL包含记录层（Record Layer）和传输层，记录层协议确定了传输层数据的封装格式。传输层安全协议使用<a title="X.509" href="https://zh.wikipedia.org/wiki/X.509">X.509</a>认证，之后利用非对称加密演算来对通信方做身份认证，之后交换对称密钥作为会谈密钥（Session key）。这个会谈密钥是用来将通信两方交换的数据做加密，保证两个应用间通信的保密性和可靠性，使客户与服务器应用之间的通信不被攻击者窃听。
> </p>

<p style="text-align: left;">
  最近，和谐物分享网站 琉璃神社 弄 TLS/SSL 加密，据说 SSL 加密能有效防范关键字重置，心血来潮我也去搞一个。
</p>

<p style="text-align: left;">
  配置 SSL 加密需要用到 SSL 证书，证书基本是收费的，而且很贵，便宜的像 Godaddy 的都比 .com 域名要贵。
</p>

<p style="text-align: left;">
  好在有一家叫 StartCom 的公司提供免费的 SSL 证书，而且证书受主流浏览器信任。
</p>

<h3 style="text-align: left;">
  Ⅰ SSL 证书的申请
</h3>

## <a href="http://www.zntec.cn/archives/startssl.html" target="_blank">免费的SSL证书提供商StartSSL详细图文注册教程 | 小蒋博客</a>

<p style="text-align: left;">
  申请挺简单，先填上个人资料注册，收邮件下一步，安装登录用的证书（记得备份），然后证书申请，填域名然后用验证。
</p>

<p style="text-align: left;">
  接着填上私钥密码，得到一串私钥，保存为 ssl.key 。
</p>

<p style="text-align: left;">
  说点插曲，我在 SSH 终端使用 vi 编辑器复制私钥进去保存，因为没有回车换行导致头行前几位字符被吞掉，然后我以为是其它原因配置出错折腾了几小时才发现是私钥错了，坑死爹了！
</p>

<p style="text-align: left;">
  <a class="lightbox" href="https://wp-archive.baka.li/2015/06/private-keys.png"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-4076" src="https://wp-archive.baka.li/2015/06/private-keys.png" alt="private-keys" width="918" height="315" srcset="https://wp-archive.baka.li/2015/06/private-keys.png 918w, https://wp-archive.baka.li/2015/06/private-keys-150x51.png 150w, https://wp-archive.baka.li/2015/06/private-keys-300x103.png 300w" sizes="(max-width: 918px) 100vw, 918px" /></a>
</p>

<p style="text-align: left;">
  得到私钥后需要解密，在终端 cd 到 ssl.key 的目录下，执行：
</p>

<pre class="lang:default decode:true  ">openssl rsa -in ssl.key -out ssl.key</pre>

<p style="text-align: left;">
  再输入密码就得到了解密的私钥。
</p>

<p style="text-align: left;">
  然后在 StartSSL 网站控制面板的 Tool Box 进入 Retrieve Certificate ，拿到申请的证书信息和公钥，保存为 ssh.crt 。
</p>

<p style="text-align: left;">
  <a class="lightbox" href="https://wp-archive.baka.li/2015/06/Retrieve-Certificate.png"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-4073" src="https://wp-archive.baka.li/2015/06/Retrieve-Certificate.png" alt="Retrieve Certificate" width="797" height="340" srcset="https://wp-archive.baka.li/2015/06/Retrieve-Certificate.png 797w, https://wp-archive.baka.li/2015/06/Retrieve-Certificate-150x64.png 150w, https://wp-archive.baka.li/2015/06/Retrieve-Certificate-300x128.png 300w, https://wp-archive.baka.li/2015/06/Retrieve-Certificate-700x300.png 700w" sizes="(max-width: 797px) 100vw, 797px" /></a>
</p>

<p style="text-align: left;">
  再在 Tool Box 的 StartCom CA Certificates 下载到 ca.pem 和 sub.class1.server.ca.pem 。
</p>

<p style="text-align: left;">
  <a class="lightbox" href="https://wp-archive.baka.li/2015/06/StartCom-CA-Certificates.png"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-4072" src="https://wp-archive.baka.li/2015/06/StartCom-CA-Certificates.png" alt="StartCom CA Certificates" width="1048" height="407" srcset="https://wp-archive.baka.li/2015/06/StartCom-CA-Certificates.png 1048w, https://wp-archive.baka.li/2015/06/StartCom-CA-Certificates-150x58.png 150w, https://wp-archive.baka.li/2015/06/StartCom-CA-Certificates-300x117.png 300w, https://wp-archive.baka.li/2015/06/StartCom-CA-Certificates-1024x398.png 1024w" sizes="(max-width: 1048px) 100vw, 1048px" /></a>
</p>

<p style="text-align: left;">
  这样证书的所有文件就搞定了，如果在文件还在本地就上传到服务器上，ssl.key、ssl.crt、ca.pem 和 sub.class1.server.ca.pem 这四个。
</p>

<h3 style="text-align: left;">
  Ⅱ Apache 配置 SSL
</h3>

<h3 style="text-align: left;">
  <a href="https://wzyboy.im/post/799.html#ch4" target="_blank">Apache + WordPress + SSL 完全指南</a>
</h3>

<p style="text-align: left;">
  用 vi 编辑器修改 Apache 的配置文件，执行：
</p>

<pre class="lang:default decode:true ">vi  /etc/apache2/sites-available/default-ssl.conf</pre>

添加修改下面的内容，证书文件路径改为自己的，我也是照别人放的。

<pre class="lang:default decode:true ">SSLEngine on
SSLCertificateFile /etc/pki/tls/certs/ssl.crt
SSLCertificateKeyFile /etc/pki/tls/private/ssl.key
SSLCertificateChainFile /etc/pki/tls/sub.class1.server.ca.pem
SSLCACertificateFile /etc/pki/tls/ca.pem</pre>

修改保存好 Apache 的配置文件后，执行：

<pre class="lang:default decode:true">a2ensite
default-ssl.conf</pre>

<p style="text-align: left;">
  确保 mod_ssl 已经开启：
</p>

<pre class="lang:default decode:true ">a2enmod ssl</pre>

最后重启 Apache ：

<pre class="lang:default decode:true ">service apache2 restart</pre>

以上只是搞定 SSL 证书的配置，还有 WordPress 方面要折腾。

<h3 style="text-align: left;">
  Ⅲ WordPress 配置 SSL
</h3>

<p style="text-align: left;">
  首先得把 WordPress 的设置里面的 Http:// 域名改为 Https:// 的，还要把数据库的文章、图片等链接全都改为 Https:// 的，用 SQL 语句或者 Velvet Blues Update URLs 插件都可以。
</p>

<p style="text-align: left;">
  <a class="lightbox" href="https://wp-archive.baka.li/2015/06/wordpress-http-https.png"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-4074" src="https://wp-archive.baka.li/2015/06/wordpress-http-https.png" alt="wordpress-http-https" width="680" height="613" srcset="https://wp-archive.baka.li/2015/06/wordpress-http-https.png 680w, https://wp-archive.baka.li/2015/06/wordpress-http-https-150x135.png 150w, https://wp-archive.baka.li/2015/06/wordpress-http-https-300x270.png 300w" sizes="(max-width: 680px) 100vw, 680px" /></a>
</p>

<p style="text-align: left;">
  接着设置 Https 跳转，编辑网站目录下的 .htaccess 文件，就是设置 <a title="炒土豆丝的 WordPress 新家：VPS ~ Ubuntu + Apache + MySQL + PHP" href="https://baka.li/vps-ubuntu-wordpress/" target="_blank">伪静态</a> 那个文件，加入下面的字段（自行修改为自己的域名）。
</p>

<pre class="lang:default decode:true ">RewriteEngine On
RewriteCond %{HTTPS} !on [NC]
RewriteCond %{HTTP_USER_AGENT} !(baiduspider|soso|bing|sogou|yahoo|sohu-search|yodao|robozilla|msnbot|msie|feedburner) [NC]
RewriteRule (.*) https://baka.li%{REQUEST_URI} [R=301,NC,L]</pre>

修改完成后再 重启 Apache ：

<pre class="lang:default decode:true ">service apache2 restart</pre>

##  Ⅳ 意外的情况

<p style="text-align: left;">
  折腾了这么久应该搞定了啊，可惜的是还没有，又遇到各种突发情况。
</p>

<p style="text-align: left;">
  1. Bilibili 外链视频无法加载，在 Http 链接下正常，只需要把 Html 外链代码的 http://share.acg.tv/flash.swf 替换成 https://static-s.bilibili.com/miniloader.swf ，SQL 语句或者插件批量替换，任君选择。
</p>

<p style="text-align: left;">
  参考：<a href="https://www.aazz.me/https-add-bilibili-videos.html" target="_blank">Https协议下插入BiliBili视频的方法</a>
</p>

<p style="text-align: left;">
  2. 多说插件出错，安装别人做的修改版多说插件（ <a href="https://github.com/yecl/duoshuo-wordpress" target="_blank" data-pjax="#js-repo-pjax-container">duoshuo-wordpress</a>），后台管理不能显示还未解决。
</p>

<p style="text-align: left;">
  参考：<a href="https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CB4QFjAA&url=https%3A%2F%2Fyecl.net%2Fssl-duoshuo-github%2F&ei=2a-IVc_yH4eA8gXhmoNA&usg=AFQjCNEVhyYLBPzhhUsxxuGPHiC7c4lHaw&sig2=cYVlAPWdFXZp7wS1IdZ5-g" target="_blank" data-href="https://yecl.net/ssl-duoshuo-github/">支持SSL的多说插件已挂到github | 夜绫千裕</a>
</p>

<p style="text-align: left;">
  3. 需要配置七牛 CDN 加速，进入七牛的管理面板，修改镜像源为 Https 链接的，并设置七牛 Https 域名，再同上修改七牛的 WordPress 加速插件。
</p>

<p class="entry-title" style="text-align: left;">
  参考：<a href="https://tumutanzi.com/archives/12128" target="_blank">试用支持HTTPS SSL的七牛云存储CDN</a>
</p>

<p class="entry-title" style="text-align: left;">
  4. 360 前端公共库不支持 SSL 只能关闭 ，Google 公共库被墙，只好用中科大提供的公共库。
</p>

<p class="entry-title" style="text-align: left;">
  插件下载：<a href="https://wordpress.org/plugins/useso-take-over-google/" target="_blank">Useso take over Google</a>
</p>

<h3 class="entry-title" style="text-align: left;">
  Ⅴ 气死强迫症
</h3>

<p class="entry-title" style="text-align: left;">
  折腾好所有后，地址栏那个绿色的小锁终于出现了。
</p>

<p class="entry-title" style="text-align: left;">
  <a class="lightbox" href="https://wp-archive.baka.li/2015/06/bakahouse-ssl.png"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-4078" src="https://wp-archive.baka.li/2015/06/bakahouse-ssl.png" alt="bakahouse-ssl" width="453" height="429" srcset="https://wp-archive.baka.li/2015/06/bakahouse-ssl.png 453w, https://wp-archive.baka.li/2015/06/bakahouse-ssl-150x142.png 150w, https://wp-archive.baka.li/2015/06/bakahouse-ssl-300x284.png 300w" sizes="(max-width: 453px) 100vw, 453px" /></a>
</p>

<p class="entry-title" style="text-align: left;">
  但是很坑爹，我把出现在首页的两篇带 Flash 视频的文章移除掉才出现绿色的小锁子，不然就是一把灰锁加一个黄色三角形。
</p>

<p class="entry-title" style="text-align: left;">
  在文章页面，因为多说插件不支持 SSL ，所以还是不绿！WTF！
</p>

<p class="entry-title" style="text-align: left;">
  <a class="lightbox" href="https://wp-archive.baka.li/2015/06/https-yellow.png"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-4080" src="https://wp-archive.baka.li/2015/06/https-yellow.png" alt="https-yellow" width="424" height="60" srcset="https://wp-archive.baka.li/2015/06/https-yellow.png 424w, https://wp-archive.baka.li/2015/06/https-yellow-150x21.png 150w, https://wp-archive.baka.li/2015/06/https-yellow-300x42.png 300w" sizes="(max-width: 424px) 100vw, 424px" /></a>
</p>

 [1]: https://zh.wikipedia.org/wiki/%E5%AE%89%E5%85%A8%E5%8D%8F%E8%AE%AE "安全协议"
 [2]: https://zh.wikipedia.org/wiki/%E7%B6%B2%E6%99%AF "网景"
 [3]: https://zh.wikipedia.org/wiki/IETF "IETF"