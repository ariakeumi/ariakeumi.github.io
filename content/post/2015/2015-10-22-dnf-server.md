---
title: PK党的福音 DNF 私服外网架设
author: 炒土豆丝
type: post
date: 2015-10-22T07:46:22+00:00
url: /dnf-server/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 17394
dsq_thread_id:
  - 4249297864
views:
  - 2817
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - ACG
  - it
tags:
  - DNF
  - 游戏

---
<div class="wp-block-image">
  <figure class="aligncenter"><a class="lightbox" href="https://wp-archive.baka.li/2015/10/Dungeon__Fighter_logo.jpg"><img loading="lazy" decoding="async" width="600" height="456" src="https://wp-archive.baka.li/2015/10/Dungeon__Fighter_logo.jpg" alt="Dungeon_&_Fighter_logo" class="wp-image-4723" srcset="https://wp-archive.baka.li/2015/10/Dungeon__Fighter_logo.jpg 600w, https://wp-archive.baka.li/2015/10/Dungeon__Fighter_logo-150x114.jpg 150w, https://wp-archive.baka.li/2015/10/Dungeon__Fighter_logo-300x228.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a>
</div>

<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    地下城与勇士，又称Dungeon & Fighter（D&F）（韩国服的英文称呼）;Dungeon and Fighter（DNF）（中国服的英文称呼），日本称“Arad战记”，美国称Dungeon Fighter Online（DFO），是一款韩国<a class="new" title="Neople（页面不存在）" href="https://zh.wikipedia.org/w/index.php?title=Neople&action=edit&redlink=1">Neople</a>（后被<a title="NEXON" href="https://zh.wikipedia.org/wiki/NEXON">NEXON</a>收购）开发的<a class="mw-redirect" title="2D" href="https://zh.wikipedia.org/wiki/2D">2D</a>横板<a title="动作游戏" href="https://zh.wikipedia.org/wiki/%E5%8A%A8%E4%BD%9C%E6%B8%B8%E6%88%8F">ACT</a>类<a title="网络游戏" href="https://zh.wikipedia.org/wiki/%E7%BD%91%E7%BB%9C%E6%B8%B8%E6%88%8F">网络游戏</a>。日本在2009年4月放映以该游戏为基础的电视动画。
  </p>
  
  <p>
    在中国DNF于2008年6月19日公测，并在2008年12月12日突破在线人数100万大关。
  </p>
  
  <p>
    DNF 台服于2012年8月31日由 garena 宣布再次代理，于2014年12月29日结束营运。
  </p>
</blockquote>

在 DNF 台服结束运营不久后，台服的服务端泄露了。现在，网上已经有了很多自建私服的教程，各种数据修改教程也很多，成为 DNF 的 GM 已经很简单了。

网上泄露的 DNF 服务端是运行着 CentOS 的&nbsp;VMware 虚拟机文件。等级还是 70 的，但是内部已经包含了大部分 80 版本的装备和地图，如发电站和镇魂图。

要想在搭建外网的 DNF 服务器，需要以下条件：

  1. 带端口转发的路由器，要功能完备需要转发十几个端口
  2. 独立的公网 IP
  3. 机器配置要好，8G 内存以上，4G 分配给虚拟机，SSD 最佳

参照下面视频搭建，只简单写下过程，用到的服务端是某猴子单数据库精简端，压缩包只有 900MB ，网上其他端都大到 5GB ，已修复 PVP ，拍卖行关闭，反正拍卖行没啥用，组队公会也正常。

需要的工具：

  * DNF CentOS 精简服务端

链接: <https://pan.baidu.com/s/1fsTxrE8YqkueLsVdhdTAHg> 提取码: snxh

  * VMware Workstation 12（精简版自行安装服务）

链接: <https://pan.baidu.com/s/1kV8Akth#list/path=%2F>

  * <a href="https://winscp.net/eng/download.php" target="_blank" rel="noopener noreferrer">WinSCP</a>
  * <a href="http://pan.baidu.com/s/1hq0eiBa" target="_blank" rel="noopener noreferrer">DNF 通用客户端</a>

链接: <https://pan.baidu.com/s/1tjKHMUrxPKhBwT4J8BPhVA> 提取码: vp4n

  * <a href="http://pan.baidu.com/s/1eQ14yWy" target="_blank" rel="noopener noreferrer">DOF 懒人专用登陆器V3.1 by kkl</a>

链接: h<ttps://pan.baidu.com/s/1W3dc_vPr4TZN0h-rFgOq4w> 提取码: g64q

视频教程：<a href="http://v.youku.com/v_show/id_XMTM1ODM5MTA0NA==.html" target="_blank" rel="noopener noreferrer">http://v.youku.com/v_show/id_XMTM1ODM5MTA0NA==.html</a>



  * ## 路由器 IP 和 HDCP 设置

进入路由器设置界面，把路由器的局域网 IP 设置为 192.168.200.1 ，一般在 “ LAN IP ” 或者 “ 局域网 IP ” 项，设置完后路由器会重启。

在通过 HDCP 服务把 192.168.200.160 这个 IP 分配给自己主机。

[<img loading="lazy" decoding="async" width="959" height="458" src="https://wp-archive.baka.li/2015/10/DNF-1.jpg" alt="DNF-1" class="wp-image-4701" srcset="https://wp-archive.baka.li/2015/10/DNF-1.jpg 959w, https://wp-archive.baka.li/2015/10/DNF-1-150x72.jpg 150w, https://wp-archive.baka.li/2015/10/DNF-1-300x143.jpg 300w" sizes="(max-width: 959px) 100vw, 959px" />][1] 

  * ## 虚拟机和桥接网卡设置

安装 VMware Workstation ，用 VM 打开 CentOS 服务端的&nbsp;CentOS.vmx 文件，这样就打开虚拟机了。

虚拟网络编辑器 Wmet 网卡设置为 “桥接模式” ，桥接到当前电脑的网卡。

虚拟机设置里的网络适配器也要改成桥接模式（直接连接物理网络）。

[<img loading="lazy" decoding="async" width="637" height="554" src="https://wp-archive.baka.li/2015/10/DNF-3.png" alt="DNF-3" class="wp-image-4702" srcset="https://wp-archive.baka.li/2015/10/DNF-3.png 637w, https://wp-archive.baka.li/2015/10/DNF-3-150x130.png 150w, https://wp-archive.baka.li/2015/10/DNF-3-300x261.png 300w" sizes="(max-width: 637px) 100vw, 637px" />][2] 

还要在控制面板的网络中心里面禁用 Vmet8 网卡。

[<img loading="lazy" decoding="async" width="825" height="426" src="https://wp-archive.baka.li/2015/10/DNF-2.png" alt="DNF-2" class="wp-image-4703" srcset="https://wp-archive.baka.li/2015/10/DNF-2.png 825w, https://wp-archive.baka.li/2015/10/DNF-2-150x77.png 150w, https://wp-archive.baka.li/2015/10/DNF-2-300x155.png 300w" sizes="(max-width: 825px) 100vw, 825px" />][3] 

  * ## 服务端网卡修改

运行虚拟机，以 root 用户名和 123456 密码登录，打开 WinSCP ，连接到虚拟机 192.168.200.131 ，用户名密码同上。

[<img loading="lazy" decoding="async" width="560" height="493" src="https://wp-archive.baka.li/2015/10/DNF-4.png" alt="DNF-4" class="wp-image-4704" srcset="https://wp-archive.baka.li/2015/10/DNF-4.png 560w, https://wp-archive.baka.li/2015/10/DNF-4-150x132.png 150w, https://wp-archive.baka.li/2015/10/DNF-4-300x264.png 300w" sizes="(max-width: 560px) 100vw, 560px" />][4] 

打开 /etc/sysconfig/network-scripts/ 目录下的 ifcfg-eth0 文件，修改为以下内容并保存。

<pre class="wp-block-code"><code>DEVICE=eth0
BOOTPROTO=static
BROADCAST=192.168.200.255
IPADDR=192.168.200.131
NETMASK=255.255.255.0
NETWORK=192.168.200.0
GATEWAY=192.168.200.1
ONBOOT=yes
USERCTL=yes</code></pre>

在到 /etc/sysconfig/ 目录下，打开 network 文件，修改为以下内容并保存。

<pre class="wp-block-code"><code>NETWORKING=yes
NETWORKING_IPV6=no
HOSTNAME=www.abc.com
GATEWAY=192.168.200.1</code></pre>

然后到虚拟机里面，运行以下命令更新网卡信息。

<pre id="block-0002409c-fe58-449a-a4c1-99416bd5203c" class="wp-block-preformatted">service network restart</pre>

  * ## &nbsp;DNF 频道 IP 设置

把 \home\dxf\channel\cfg 目录下的 channel.cfg 配置文件中 “ this_ip ”  替换为自己的公网 IP，[公网 IP 查询][5]，像下面这样。

<pre class="wp-block-code"><code>&#091;server]
max_client = 1000 
this_ip = 你的公网 IP
this_tcp_port = 7001
this_udp_port = 7001

bridge_ip = 192.168.200.131
bridge_port = 7000
id = 3</code></pre>

这个 900MB 的 CentOS 服务端默认开启了两个频道，它们的配置文件在&nbsp;/home/dxf/game/cfg 目录，cain01.cfg 为 11 频道，cain03.cfg 为52 频道（决斗场）。

把两个文件里面的以下行的 IP 替换为自己的公网 IP ，一共八行。

<pre class="wp-block-code"><code>ip = 公网 IP 
udp_ip_of_hades = 公网 IP 
ipg_ip = 公网 IP 
nxj_ipg_ip = 公网 IP 
relay_ip = 公网 IP 
stun_ip = 公网 IP 
stun_ip = 公网 IP 
stun_ip = 公网 IP</code></pre>

因为公网 IP 会经常变动，所以以上几个文件的公网 IP 也要跟着改。

  * ## 路由器端口转发设置

进入路由 端口转发/端口映射 设置页面，添加以下转发。

<pre class="wp-block-preformatted">7001  Tcp 大区端口 
7000    Upd 大区端口
10011   Tcp ch.11
10031   Tcp ch.52
组队相关
31003   Upd+Tcp
9006    Upd+Tcp
7200    Upd+Tcp
2311    Upd+Tcp
2312    Upd+Tcp
2313    Upd+Tcp
工会好友
11011   Upd ch.11
11031   Upd ch.52
10052   Tcp ch.52
11052   Tcp ch.52


以上转发到 192.168.200.131</pre>

  * ## 最后的配置和登录

Script.pvf 文件保存着 NPC、商城、商品价格、地图装备属性甚至装备爆率等配置信息，服务端它中在 /home/dxf/game 目录下，客户端的在客户端根目录，要保证服务端和客户端的&nbsp;Script.pvf 文件是一致的，不然购买物品时会网络中断。

Script.pvf 文件可以从其它私服提取，或者在网上找别人发布的，如果不介意甚至可以用官方的，但一定要保持客户端和服务端&nbsp;Script.pvf 文件的一致，请自行配置。

公钥 publickey.pem 则是和登录器验证的，用 WinSCP 把&nbsp;<a href="http://pan.baidu.com/s/1pJ5p96V" target="_blank" rel="noopener noreferrer">DNF简易登录器</a>&nbsp;里面的 publickey.pem 覆盖到&nbsp;/home/dxf/game 目录下，DNFLogin 则放到客户端根目录。

都搞好后就可以在虚拟机中启动服务端，输入以下命令回车启动：

<pre class="wp-block-preformatted">./run</pre>

出现以下画面说明 DNF 服务端已成功启动（俗称五国），就可以进游戏了。

[<img loading="lazy" decoding="async" width="463" height="440" src="https://wp-archive.baka.li/2015/10/DNF-6.png" alt="DNF-6" class="wp-image-4705" srcset="https://wp-archive.baka.li/2015/10/DNF-6.png 463w, https://wp-archive.baka.li/2015/10/DNF-6-150x143.png 150w, https://wp-archive.baka.li/2015/10/DNF-6-300x285.png 300w" sizes="(max-width: 463px) 100vw, 463px" />][6] 

在 DNF 懒人登录器里面输入公网 IP 就可以登录账号了，注册账号还要在数据库配置里面输入公网 IP 。

这个登录器需要转发数据库端口，也就是说别人知道了你的公网 IP 后可以黑进你的数据库，所以此登录器仅适合很少开服，只和朋友玩的服务器。

需要网关的开服用登录器配置现在就不写了。

[<img loading="lazy" decoding="async" width="558" height="421" src="https://wp-archive.baka.li/2015/10/DNF-7.jpg" alt="DNF-7" class="wp-image-4706" srcset="https://wp-archive.baka.li/2015/10/DNF-7.jpg 558w, https://wp-archive.baka.li/2015/10/DNF-7-150x113.jpg 150w, https://wp-archive.baka.li/2015/10/DNF-7-300x226.jpg 300w" sizes="(max-width: 558px) 100vw, 558px" />][7] 

组队或者 PVP 成功就是完美的外网架设了。

这版本 PVP 伤害有问题，一身 12 或者 13 红字体力的装备和零强化武器 PK 最佳。

[<img loading="lazy" decoding="async" width="1024" height="768" src="https://wp-archive.baka.li/2015/10/DNF-PVP-HUB.jpg" alt="DNF-PVP-HUB" class="wp-image-4753" srcset="https://wp-archive.baka.li/2015/10/DNF-PVP-HUB.jpg 1024w, https://wp-archive.baka.li/2015/10/DNF-PVP-HUB-150x113.jpg 150w, https://wp-archive.baka.li/2015/10/DNF-PVP-HUB-300x225.jpg 300w" sizes="(max-width: 1024px) 100vw, 1024px" />][8]

 [1]: https://wp-archive.baka.li/2015/10/DNF-1.jpg
 [2]: https://wp-archive.baka.li/2015/10/DNF-3.png
 [3]: https://wp-archive.baka.li/2015/10/DNF-2.png
 [4]: https://wp-archive.baka.li/2015/10/DNF-4.png
 [5]: http://ip138.com/
 [6]: https://wp-archive.baka.li/2015/10/DNF-6.png
 [7]: https://wp-archive.baka.li/2015/10/DNF-7.jpg
 [8]: https://wp-archive.baka.li/2015/10/DNF-PVP-HUB.jpg