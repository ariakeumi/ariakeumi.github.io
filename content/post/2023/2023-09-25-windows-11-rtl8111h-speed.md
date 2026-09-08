---
title: Windows 11 系统的 RealTek RTL8111H 千兆有线网卡的微软公版驱动无法满速问题
author: 炒土豆丝
type: post
date: 2023-09-25T11:41:01+00:00
url: /windows-11-rtl8111h-speed/
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 277
categories:
  - app
tags:
  - Windows

---


## 发现问题 

在 PC 和 NAS 之间拷文件的时候发现速度只有 90MB/s ，起初没太在意，毕竟 NAS 换了 UNRAID 系，可能是 SMB 协议问题，也可能是 UNRAID 的磁盘阵列速度就是慢。

再给 NAS 升级了双 NVME SSD 的 ZFS 阵列后，拷贝速度还是一样跑不满千兆，开始排查原因。

用 iperf3 测速，速度稳定 780Mbps ，排除 NAS 的硬盘速度的问题。

网线，换过。网卡协商速度是 1Gbps ，也没问题。

接着换 Mac mini 跑 iperf3 ，能跑满千兆。

那就是 PC 的问题了。

我网卡是螃蟹的 RealTek RTL8111H 千兆网卡，用的是 Windows 11 的公版驱动，自从 WIN10 开始我只手动安装显卡驱动，其他的都是微软推送啥我用啥了。

## 驱动更新 

主板官网上不提供 Windows 11 的有线网卡驱动，还得去螃蟹网站上找，他们网站做的真的很反人类&#8230;

[Realtek PCIe FE / GBE / 2.5G / 5G Ethernet Family Controller Software][1]

下载 Win11 Auto Installation Program (NetAdapterCx) 然后安装，速度恢复千兆&#8230;

Windows Update 推送的驱动真的不可靠啊，不知道是 RTL8111H 网卡特有的问题还是所有螃蟹网卡微软驱动都有问题，建议用微软公版网卡驱动的都测下速度。

## 微软公版驱动 

[<img loading="lazy" decoding="async" width="1227" height="600" src="https://wp-archive.baka.li/2023/09/ms-lan-driver.png" alt="" class="wp-image-6724" />][2] 

## 螃蟹驱动 

[<img loading="lazy" decoding="async" width="988" height="666" src="https://wp-archive.baka.li/2023/09/image.png" alt="此图片的alt属性为空；文件名为Realtek-lan-driver.png" class="wp-image-6726" />][3]

[1]: https://www.realtek.com/Download/List?cate_id=584
[2]: https://wp-archive.baka.li/2023/09/ms-lan-driver.png
[3]: https://wp-archive.baka.li/2023/09/image.png