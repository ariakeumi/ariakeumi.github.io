---
title: 红米 AX6000 路由器配置 AdGuard Home + OpenClash
author: 炒土豆丝
type: post
date: 2023-04-30T16:33:00+00:00
url: /redmi-ax6000-adguard-home-openclash/
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - 'false'
argon_show_post_outdated_info:
  - default
views:
  - 479
categories:
  - it
  - app
tags:
  - 翻墙
  - 路由器

---
 

我现在使用路由器是红米 AX6000 ，使用的固件是 237176253 大佬的 <a href="https://www.right.com.cn/forum/thread-8261104-1-1.html" target="_blank" rel="noreferrer noopener">红米ax6000闭源驱动op</a> 固件，之前用的是 广告过滤大师 Plus+ （adbyby），不过它在 237 的新固件上会导致防火墙无法重启，不得已要换到 AdGuard Home 。

AdGuard Home + OpenClash 的配置方法花样百出，各种教程看得我这种网络小白头晕，最后我决定参照 OpenClash 原作者<a href="https://github.com/vernesong/OpenClash/discussions/1420" target="_blank" rel="noreferrer noopener">推荐的方法</a>配置，中间遇到点小插曲，就把过程写一下吧。

## OpenClash 配置 

OpenClash 运行模式使用 **Redir-Host (兼容) 模式** 。把 OpenClash 界面的 **插件设置** &#8211; **DNS 设置** 选项的 **本地 DNS 劫持** 给停用。

<img loading="lazy" decoding="async" width="1001" height="852" src="https://wp-archive.baka.li/2023/04/openclash-conf-1.png" alt="" class="wp-image-6551" />  

接着把 **覆写设置** &#8211; **DNS 设置** 的 ***自定义上游 DNS 服务器** 给勾选，下面的上游 DNS 服务器用默认的配置就行。

<img loading="lazy" decoding="async" width="967" height="732" src="https://wp-archive.baka.li/2023/04/openclash-conf-2.png" alt="" class="wp-image-6552" />  

## 安装 AdGuard Home 

因为刷的是 mini 版不带 AdGuard Home ，软件源也没有 luci 界面的，就是 Github 上找了这个：

<a href="https://github.com/kongfl888/luci-app-adguardhome" target="_blank" rel="noreferrer noopener">kongfl888/luci-app-adguardhome</a>

把 .ipk 上传到路由器，在 SSH 上用 opkg 命令安装。

<pre class="wp-block-code"><code>opkg install luci-app-adguardhome_1.8-20221120_all.ipk
opkg install luci-i18n-adguardhome-zh-cn_git-22.323.68542-450e04a_all.ipk
</code></pre>

我再安装完后 OpenWrt 界面 变成了英文，语言设置里只有 auto 选项，要先卸载了中文语言包再重新安装才变回中文。

<pre class="wp-block-code"><code>opkg update
opkg remove luci-i18n-base-zh-cn
opkg install luci-i18n-base-zh-cn</code></pre>

## 配置 AdGuard Home 

在 AdGuard Home 的界面点击更新核心版本，然后进入配置界面。

端口保持默认的 3000 就行。

<img loading="lazy" decoding="async" width="792" height="622" src="https://wp-archive.baka.li/2023/04/adg-install-2.png" alt="" class="wp-image-6549" />  

DNS 端口填 5553 。

<img loading="lazy" decoding="async" width="784" height="646" src="https://wp-archive.baka.li/2023/04/adg-install-3.png" alt="" class="wp-image-6550" />  

AdGuard Home **设置** &#8211; **DNS 设置** &#8211; **上游 DNS 服务器** 填写 OpenClash 的 DNS 地址 127.0.0.1:7874 和 114.114.114.114 ，填 114 DNS 是为了防止 OpenClash 关闭时能正常访问国内网站。

<img loading="lazy" decoding="async" width="1001" height="638" src="https://wp-archive.baka.li/2023/04/adg-conf.png" alt="" class="wp-image-6553" />  

回到 AdGuard Home 的 Luci 界面把 5553重定向 改为 重定向53端口到AdGuard Home ，最后启用。

<img loading="lazy" decoding="async" width="794" height="599" src="https://wp-archive.baka.li/2023/04/adg-install-1.png" alt="" class="wp-image-6546" />  

配置完成后在 OpneWrt 的防火墙里面，可以看到 udp dpt:53 redir ports 5553 这条规则是在 /\* DNSMASQ \*/ udp dpt:53 redir ports 53 下面的。

<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    OpenClash 作者提到：
  </p>
  
  <cite>应用配置后确保防火墙中的这条规则在下面那条DNSMASQ规则之前，否则请尝试前往网络-防火墙-自定义规则，注释掉系统默认的转发到53端口的规则。</cite>
</blockquote>

但在 237 大佬编译的 OpenWrt 固件里防火墙自定义规则是空的，一番摸索后发现，把 **DHCP/DNS** &#8211; **服务器设置** &#8211; **常规设置** 的 **DNS 重定向** 取消勾选并保存应用，然后重新勾选再保存应用上，防火墙的 udp dpt:53 redir ports 5553 规则就在 /\* DNSMASQ \*/ udp dpt:53 redir ports 53 上面了。

有更好设置方法的大佬也可以告诉我下。

<img loading="lazy" decoding="async" width="671" height="304" src="https://wp-archive.baka.li/2023/04/openwrt-firewall.png" alt="" class="wp-image-6554" />  

## 运行效果 

<img loading="lazy" decoding="async" width="1325" height="771" src="https://wp-archive.baka.li/2023/04/adguard-home.png" alt="" class="wp-image-6545" /> 