---
title: 路由器 CPU 性能天梯排行榜
author: 炒土豆丝
type: post
date: 2023-09-20T23:44:29+00:00
url: /router-cpu-coremark/
featured_image: https://wp-archive.baka.li/2023/09/coremark-poster.png
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 276
categories:
  - app
tags:
  - 路由器
  - OpenWrt

---
本人为了选购路由器从网络上收集了数个路由器的 CoreMark 跑分， 包括了硬路由、X86 软路由和 ARM 软路由等。CoreMark 分数仅代表了路由器的处理器性能，和路由器的信号、NAT 转发性能等没有关联，仅供选购路由器时参考，更多路由器的拆机评测可以去 [ACWIFI 网站][1] 上看。<figure class="wp-block-pullquote">

> CoreMark是一款专门用于测量嵌入式处理器和微控制器性能的小型基准测试软件。它使用一系列测试程序来测量处理器性能，包括加密解密、压缩解压缩、矩阵操作、排序、字符串操作等多项测试，提供一个标准化的得分称为CoreMark得分。 

如果你有其他的路由器 CoreMark 跑分也可以分享给我。

|芯片厂商|处理器型号|产品型号|规格|CoreMark ≈ 分数|
|:----|:----|:----|:----|:----|
|AMD|5800H|SER5Pro|八核 Zen3|300000|
|AMD|5600H|SER5Pro|六核 Zen3|240000|
|Intel|N305|畅网 N305|八核 x86|199000|
|Intel|N100|EQ12|四核 x86|100000|
|Rockchip|RK3588S|NanoPi R6S|四核 A76 + 四核 A55|99000|
|Intel|Celeron N5105|N/A|四核 x86|77000|
|Intel|Celeron J4125|N/A|四核 x86|61000|
|Qualcomm|IPQ9570|小米万兆路由器|四核 A73|49000|
|Rockchip|RK3399|NanoPi R4S|双核 A73 + 四核 A55|40000|
|Intel|Celeron J1900|N/A|四核 x86|34000|
|Qualcomm|IPQ9554|小米 BE7000|四核 A73|33000|
|Broadcom|BCM2711|树莓派 4B|四核 A73|32500|
|Qualcomm|IPQ8072A|小米 AX9000|四核 A53|29909|
|MediaTek|MT7986A|红米 AX6000|四核 A53|27500|
|Rockchip|RK3568|NanoPi R5S|四核 A55|26000|
|Qualcomm|IPQ6018|360v6|四核 A53|20000|
|Qualcomm|IPQ8074|华硕 RT-AX89X|四核 A53|N/A|
|Intel|Celeron J1800|N/A|双核 x86|18200|
|Rockchip|RK3328|NanoPi R2S|四核 A55|18000|
|Amlogic|S905D|斐讯 N1|四核 A53|18400|
|Qualcomm|IPQ8071A|红米 AX6|四核 A53|17500|
|Broadcom|BCM4908|华硕 AX88U|四核 A53|N/A|
|Broadcom|BCM4709C|斐讯 K3|双核 A9|9700|
|MediaTek|MT7622B|红米 AX6S|双核 A53|9300|
|MediaTek|MT7981|360 T7|双核 A53|8800|
|MediaTek|MT7621|斐讯 K2P A1|双核 MIPS|4900|
|MediaTek|MT7620A|斐讯 K2|单核 MIPS|1250|
|Qualcomm|IPQ5018|小米 AX6000|双核 A53|N/A|

[1]: https://www.acwifi.net/
