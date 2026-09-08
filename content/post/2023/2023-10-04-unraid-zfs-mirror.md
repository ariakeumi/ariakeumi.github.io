---
title: 绿联 DX4600 的 UNRAID 系统折腾后篇
author: 炒土豆丝
description: "UNRAID 系统双 NVME SSD 组 ZFS 镜像阵列"
type: post
date: 2023-10-04T04:07:00+00:00
url: /unraid-zfs-mirror/

categories:
  - app
  - it
tags:
  - NAS
---
 

在上一篇的 《<a href="https://baka.li/dx4600-unraid/" target="_blank" rel="noreferrer noopener">绿联 DX4600 安装 UNRAID 系统</a>》 里我介绍了安装 UNRAID 系统、启动阵列和插件相关的内容。

此时我的 NAS 上有 4 块硬盘，一块 M.2 NVME SSD，一块 2.5寸 SSD，一块 2.5寸 HDD，一块 3.5寸 HDD。

NVME SSD 上建立的 appdata 、system 和 domains 目录存放 Docker 和 虚拟机文件，2.5寸 SSD 直通给黑群晖虚拟机，存放杂乱资料和音乐、照片等，2.5寸 HDD 备份 UNRAID 和黑群晖文件，3.5寸 HDD 存放电影电视剧和色情影片等视频。

最近朋友送了块 M.2 NVME SSD 给我，容量和 NAS 上的一样是 256GB 的，正好打算组个 RAID1 阵列，保证 NAS 上的部署的 Docker 和虚拟机文件的安全，下面介绍怎么添加 ZFS 阵列。

## Brtfs RAID 和 ZFS Mirror 

UNRAID 6.12 系统支持添加 Brtfs 文件系统的 RAID1 和 ZFS 文件系统的 Mirror 两种镜像阵列。

我简单测试了下两个不同文件系统的写入速度，发现还是 ZFS Mirror 速度更快。

Brtfs RAID1 写入性能

<pre class="wp-block-code"><code>root@Unraid:/mnt# time dd if=/dev/zero of=/mnt/ssd/test bs=10M count=1000
1000+0 records in
1000+0 records out
10485760000 bytes (10 GB, 9.8 GiB) copied, 48.5576 s, 216 MB/s

real    0m48.561s
user    0m0.005s
sys     0m6.351s
root@Unraid:/mnt# time dd if=/dev/zero of=/mnt/ssd/test bs=10M count=1000
1000+0 records in
1000+0 records out
10485760000 bytes (10 GB, 9.8 GiB) copied, 66.9611 s, 157 MB/s

real    1m9.187s
user    0m0.006s
sys     0m8.656s
root@Unraid:/mnt# time dd if=/dev/zero of=/mnt/ssd/test bs=10M count=1000
1000+0 records in
1000+0 records out
10485760000 bytes (10 GB, 9.8 GiB) copied, 41.3933 s, 253 MB/s

real    0m43.469s
user    0m0.002s
sys     0m8.523s</code></pre>

ZFS Mirror 写入性能

<pre class="wp-block-code"><code>root@Unraid:/mnt# time dd if=/dev/zero of=/mnt/ssd/test bs=10M count=1000
1000+0 records in
1000+0 records out
10485760000 bytes (10 GB, 9.8 GiB) copied, 25.8515 s, 406 MB/s

real    0m25.855s
user    0m0.009s
sys     0m5.025s

root@Unraid:/mnt# time dd if=/dev/zero of=/mnt/ssd/test bs=10M count=1000
1000+0 records in
1000+0 records out
10485760000 bytes (10 GB, 9.8 GiB) copied, 37.2333 s, 282 MB/s

real    0m37.243s
user    0m0.009s
sys     0m4.845s

root@Unraid:/mnt# time dd if=/dev/zero of=/mnt/ssd/test bs=10M count=1000
^C184+0 records in
184+0 records out
1929379840 bytes (1.9 GB, 1.8 GiB) copied, 3.41175 s, 566 MB/s

real    0m3.421s
user    0m0.002s
sys     0m0.880s</code></pre>

## 添加 ZFS 镜像阵列 

先备份好 appdata 、system 和 domains 目录。

在 主界面 的池设备里添加两个插槽的存储池，命名随意。

[<img loading="lazy" decoding="async" width="759" height="379" src="https://wp-archive.baka.li/2023/09/unraid-ssd-pool-1.png" alt="" class="wp-image-6719" />][1] 

文件系统类型选择 ZFS 镜像，一组两设备，其他默认，格式化然后启动阵列。

[<img loading="lazy" decoding="async" width="1315" height="706" src="https://wp-archive.baka.li/2023/09/unraid-ssd-zfs-pool.png" alt="" class="wp-image-6712" />][2] 

添加共享目录，主存储空间选择刚才建立名为 SSD 的 ZFS 阵列。

[<img loading="lazy" decoding="async" width="1164" height="521" src="https://wp-archive.baka.li/2023/09/unraid-ssd-domains.png" alt="" class="wp-image-6713" />][3] 

## 修改 Docker 和虚拟机文件路径 

把备份好的 appdata 、system 和 domains 目录拷贝回新建立的 /mnt/ssd 目录里。

在 设置 &#8211; 虚拟机管理器 的 Libvirt 存储位置，由原来的 /mnt/user/system/libvirt/libvirt.img 改为 /mnt/ssd/system/libvirt/libvirt.img 。默认虚拟机存储路径同上。

设置 &#8211; Docker &#8211; Docker虚拟磁盘大小 目录也改成 /mnt/ssd/system/docker/docker.img ，默认应用数据存储位置 同上。

简单几下，就把 UNRAID 的单盘文件迁移到镜像阵列里了，不用再担心 SSD 突然挂掉导致应用配置丢失。

[<img loading="lazy" decoding="async" width="1265" height="744" src="https://wp-archive.baka.li/2023/09/unraid-dashboard-2023.png" alt="" class="wp-image-6716" />][4]

 [1]: https://wp-archive.baka.li/2023/09/unraid-ssd-pool-1.png
 [2]: https://wp-archive.baka.li/2023/09/unraid-ssd-zfs-pool.png
 [3]: https://wp-archive.baka.li/2023/09/unraid-ssd-domains.png
 [4]: https://wp-archive.baka.li/2023/09/unraid-dashboard-2023.png