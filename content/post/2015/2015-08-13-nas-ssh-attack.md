---
title: 黑群晖 NAS 遭到 SSH 密码暴力穷举攻击
author: 炒土豆丝
type: post
date: 2015-08-13T10:43:43+00:00
url: /nas-ssh-attack/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 5695
dsq_thread_id:
  - 4032009128
views:
  - 1123
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - otaku
tags:
  - NAS
  - 黑群晖

---
今天登陆 DSM 弹出一堆警告信息，原来有大量不明 IP 地址 SSH 登录失败被封锁了。

我的黑群晖设置了 DDNS ，方便远程访问，SSH 偶尔会用所以没关，结果被黑客盯上。

[<img loading="lazy" decoding="async" width="1078" height="687" src="https://wp-archive.baka.li/2015/08/Host-was-blocked-via-SSH.png" alt="Host was blocked via SSH" class="wp-image-4516" srcset="https://wp-archive.baka.li/2015/08/Host-was-blocked-via-SSH.png 1078w, https://wp-archive.baka.li/2015/08/Host-was-blocked-via-SSH-150x96.png 150w, https://wp-archive.baka.li/2015/08/Host-was-blocked-via-SSH-300x191.png 300w, https://wp-archive.baka.li/2015/08/Host-was-blocked-via-SSH-1024x653.png 1024w" sizes="(max-width: 1078px) 100vw, 1078px" />][1] 

好在我开启了自动封锁（控制面板 &#8211; 安全性），5分钟内登录失败5次就会封锁 IP ，有23个 IP 被封锁，也就是说黑客穷举了至少 115 个密码。

前段时间有新闻说群晖系统遭入侵，硬盘数据被加密，如果不按要求支付比特币给黑客数据就会被销毁。所以，做好安全防护吧。

  * 设置更严格的封锁机制
  * 设置好邮件通知，以便应付紧急情况，因为我的邮件通知没设置好导致过了一天才知道被攻击
  * 必要情况下关闭 SSH 甚至 DDNS

 [1]: https://wp-archive.baka.li/2015/08/Host-was-blocked-via-SSH.png