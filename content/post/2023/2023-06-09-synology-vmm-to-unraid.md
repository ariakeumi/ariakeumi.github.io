---
title: 群晖 VMM 虚拟机迁移到 UNRAID 平台
author: 炒土豆丝
type: post
date: 2023-06-08T17:32:55+00:00
url: /synology-vmm-to-unraid/
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 431
categories:
  - app
tags:
  - NAS

---
原来有一台部署在群晖 Virtual Machine Manager (VMM) 平台的 <a href="https://baka.li/dnf-server/" target="_blank" rel="noreferrer noopener">DNF 私服</a> 游戏服务器，它运行的是 CentOS 5.9 系统，以前是从 VMware 迁移过去的，由于没有再玩 DNF 了就吃灰很久了。

最近升级了 <a href="https://baka.li/dx4600-unraid/" target="_blank" rel="noreferrer noopener">DX4600 NAS</a> 后想着也把它也迁移到 UNRAID 上，水平太菜一路上踩了不少坑，简单记录过程&#8230;

## 导出 VMM 虚拟机 

直接导出为常规 OVA 就行了。

[<img loading="lazy" decoding="async" width="1074" height="669" src="https://wp-archive.baka.li/2023/06/synology-vmm-export.png" alt="" class="wp-image-6643" />][1] 

## 转换镜像格式 

把导出的 OVA 镜像拷贝到 UNRAID 上，进入 UNRAID 系统的终端，先用 tar xvf 命令解包，再把得到 vmdk 镜像转换为 qcow2 镜像。

<pre class="wp-block-code"><code>tar xvf dnf.ova
qemu-img convert -f vmdk -O qcow2 dnf-disk1.vmdk dnf.qcow2</code></pre>

解包 OVA 镜像后还会出线一个 ovf 的虚拟机配置文件，可能需要参考它来配置新的虚拟机。

## 配置虚拟机 

因为是很老的系统，所以机器选择 i440fx ，BIOS 选择 SeaBIOS 。

主要虚拟磁盘位置，设置为手动，路径填转换好的 qcow2 镜像的路径。

虚拟磁盘总线照 ovf 配置文件填的 SATA ，网卡 E1000 和 Virtio 都可以，其他默认就行。

[<img loading="lazy" decoding="async" width="907" height="666" src="https://wp-archive.baka.li/2023/06/unraid-dnf-server.png" alt="" class="wp-image-6645" />][2] 

## DNF！启动！ 

看到老游戏又跑起来了还是有点小开心的。

[<img loading="lazy" decoding="async" width="1645" height="813" src="https://wp-archive.baka.li/2023/06/DNF-Start.png" alt="" class="wp-image-6646" srcset="https://wp-archive.baka.li/2023/06/DNF-Start.png 1645w, https://wp-archive.baka.li/2023/06/DNF-Start-1536x759.png 1536w" sizes="(max-width: 1645px) 100vw, 1645px" />][3]

 [1]: https://wp-archive.baka.li/2023/06/synology-vmm-export.png
 [2]: https://wp-archive.baka.li/2023/06/unraid-dnf-server.png
 [3]: https://wp-archive.baka.li/2023/06/DNF-Start.png