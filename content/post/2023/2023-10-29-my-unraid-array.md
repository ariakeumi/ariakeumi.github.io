---
title: UNRAID 系统添加校验盘和 ZFS 镜像阵列升级
author: 炒土豆丝
type: post
date: 2023-10-29T05:16:46+00:00
url: /my-unraid-array/
featured_image: https://wp-archive.baka.li/2023/10/unraid-poster.png
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 219
categories:
  - it
tags:
  - NAS

---
 

应该是绿联 DX4600 NAS 折腾 UNRAID 系统系列的最后一篇了，后期再添加一块 10TB 硬盘也算毕业了。

## 升级内容 

  1. 原 10TB +2TB 的存储空间，再添加一个 10TB 存储盘和一个 10TB 校验盘
  2. 原 256GB 的 ZFS 镜像系统盘，升级到1TB 

新购置的硬盘：

西数 HC330 ，10TB 空气盘，海康 OEM 版本，PDD 880 元购入 。

西数 HC510 ，10TB 氦气盘，服务器拆机，通电 3000 小时，淘宝北京某商家 550 元购入。

海力士 Gold P31 ，1TB NVME SSD ，京东首发 370 元，号称最强 PCI-E 3.0 的 SSD。

[<img loading="lazy" decoding="async" width="2016" height="1512" src="https://wp-archive.baka.li/2023/10/new-hard-drive.webp" alt="" class="wp-image-6741" srcset="https://wp-archive.baka.li/2023/10/new-hard-drive.webp 2016w, https://wp-archive.baka.li/2023/10/new-hard-drive-1536x1152.webp 1536w" sizes="(max-width: 2016px) 100vw, 2016px" />][1] 

## ZFS 镜像阵列升级 

原来的是两个 256GB SSD 的 ZFS 镜像，先备份了数据，然后拆下一块 256GB SSD，把新买的海力士 P31 替换上去。

镜像同步速度 720MB/s 左右， P31 最高温度是 57 度，比我想象的要高。

[<img loading="lazy" decoding="async" width="826" height="453" src="https://wp-archive.baka.li/2023/10/zfs-mirror-sync.png" alt="" class="wp-image-6743" />][2] [<img loading="lazy" decoding="async" width="1295" height="589" src="https://wp-archive.baka.li/2023/10/zfs-mirror-speed.png" alt="" class="wp-image-6742" />][3] 

镜像同步完成后再替换上另一块 1TB 的 SSD，这块大华 C900 PLUS 是我电脑上拆下的，无缓盘，PDD 200元的历史低点购入，据说容易掉盘，所以搭配上了一块以可靠性著称的 P31 。

等镜像同步完后存储空间就直接从 256GB 变成 1TB 了。

这 1TB 的存储空间直接作为 docker 和 虚拟机数据盘的同时，还作为 UNRAID 阵列的缓存。

[<img loading="lazy" decoding="async" width="1504" height="1340" src="https://wp-archive.baka.li/2023/10/new-zfs-mirror.webp" alt="" class="wp-image-6744" />][4] 

## 添加校验盘 

原来的阵列是一块 10TB 5200 转的 HE10 氦气盘和 2TB 紫盘，后期要升级的话就是把 2TB 的紫盘替换成 10TB 的。

[<img loading="lazy" decoding="async" width="2016" height="1512" src="https://wp-archive.baka.li/2023/10/new-drive-array.webp" alt="" class="wp-image-6745" style="aspect-ratio:1.3333333333333333;width:840px;height:auto" srcset="https://wp-archive.baka.li/2023/10/new-drive-array.webp 2016w, https://wp-archive.baka.li/2023/10/new-drive-array-1536x1152.webp 1536w" sizes="(max-width: 2016px) 100vw, 2016px" />][5] [<img loading="lazy" decoding="async" width="1067" height="590" src="https://wp-archive.baka.li/2023/10/unraid-array-add.png" alt="" class="wp-image-6750" />][6] 

添加完硬盘后开始进行奇偶校验，以前校验的速度只有 100MB/s 出头，因为速度受限于最慢的那块西数 2TB 紫盘，当校验超过 2TB 后，速度开始达到 200MB/s ，不过最后校验完还是花了 18 小时。

[<img loading="lazy" decoding="async" width="637" height="762" src="https://wp-archive.baka.li/2023/10/unraid-array-check.png" alt="" class="wp-image-6747" />][7] [<img loading="lazy" decoding="async" width="1270" height="673" src="https://wp-archive.baka.li/2023/10/unraid-array.png" alt="" class="wp-image-6746" />][8] 

## 硬盘温度 

在室温 30.5 度的情况下， 海力士 P31 待机(超低负载) 温度在 47 度左右，尚可接受，没有 DRAM 缓存的 大华 C900 PLUS 就低很多了。

到机械盘这边，无论是 5200转 还是 7200 转的10TB 氦气盘，待机温度都在 40 度以内，表现优秀。

10TB 空气盘的 HC330 则非常糟糕，待机 (无读写) 就 44 到 45 度，比氦气盘高了五六度，在进行校验的时候我必须把风扇转速拉满，不然突破五十度是肯定的。

原本打算最后一个盘升级的时候选 10TB 的希捷 7E10 空气盘，现在已经不考虑了。

空气盘比氦气盘真的热太多太多了，NAS 不建议选择 10TB 的空气盘，据说 8TB 的温度会好不少。

 [1]: https://wp-archive.baka.li/2023/10/new-hard-drive.webp
 [2]: https://wp-archive.baka.li/2023/10/zfs-mirror-sync.png
 [3]: https://wp-archive.baka.li/2023/10/zfs-mirror-speed.png
 [4]: https://wp-archive.baka.li/2023/10/new-zfs-mirror.webp
 [5]: https://wp-archive.baka.li/2023/10/new-drive-array.webp
 [6]: https://wp-archive.baka.li/2023/10/unraid-array-add.png
 [7]: https://wp-archive.baka.li/2023/10/unraid-array-check.png
 [8]: https://wp-archive.baka.li/2023/10/unraid-array.png