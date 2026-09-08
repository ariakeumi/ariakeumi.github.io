---
title: 博客域名 NS 从 DNSPOD 转移到 Cloudflare
author: 炒土豆丝
type: post
date: 2024-04-09T22:54:21+00:00
url: /dnspod-to-cloudflare/
image: "https://wp-archive.baka.li/2024/04/cloudflare.webp"
views:
  - 48
categories:
  - it
tags:
  - 域名

---
## 吐槽 

博客的 umi.im 域名 NS 设置在 DNSPOD ，近期经常修改子域名的 DNS 解析，结果每次登录 DNSPOD 都要我输入烦人的验证码，加上眼馋 Cloudflare 的各种免费服务，萌生了转移域名 NS 的想法。

## Cloudflare NS 的优点 

Cloudflare Pages 、R2 对象存储和 Tunnels 等服务可以绑定到子域名，很快我就把 <a href="https://me.umi.im/" target="_blank" rel="noreferrer noopener">Contact me</a> 和 [DNF土豆服PVP排行榜][1] 两个页面挂到了 CF Pages 上，再用 Cloudflare Workers 弄了个 <a href="https://ip.umi.im/" target="_blank" rel="noreferrer noopener">IP-Check</a> 接口。

当然最重要的是被 DDOS 的时候可以马上直接套 CF 的 CDN ，可惜没人攻击我网站。

## 转移过程 

在 Cloudflare 添加网站，会提示你去修改域名 NS ，接着去购买域名的网站把 NS 改成 CF 的，选择 Free 套餐。

[<img loading="lazy" decoding="async" width="666" height="479" src="https://wp-archive.baka.li/2024/04/change-cloudflare-ns.png" alt="" class="wp-image-6804" />][2] 

由于 DNS 记录很多，还需要从 DNSPOD 导出域名记录，导出格式选 ZONE 文件，就可以把 DNS 记录都导入 CF 了。

[<img loading="lazy" decoding="async" width="695" height="347" src="https://wp-archive.baka.li/2024/04/dnspod-export.png" alt="" class="wp-image-6805" />][3] 

## 中国大陆解析情况 

其实很早就想把 NS 改成 CF 的了，但听说中国大陆地区有很多地方解析不了。

用 ITDOG 的测试看了下，只有重庆的运营商 DNS 解析错误，泉州无法访问是防火墙白名单的原因。

本来就是 1IP 博客，不差这点流量。

[<img loading="lazy" decoding="async" width="963" height="338" src="https://wp-archive.baka.li/2024/04/cloudflare-dns-china.png" alt="" class="wp-image-6806" />][4]

[1]: https://dnf.umi.im/
[2]: https://wp-archive.baka.li/2024/04/change-cloudflare-ns.png
[3]: https://wp-archive.baka.li/2024/04/dnspod-export.png
[4]: https://wp-archive.baka.li/2024/04/cloudflare-dns-china.png