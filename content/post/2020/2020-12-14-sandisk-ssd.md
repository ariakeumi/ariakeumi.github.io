---
title: 一块使用六年写入 240TB 的 SSD 是什么样子？
author: 炒土豆丝
type: post
date: 2020-12-13T16:45:03+00:00
url: /sandisk-ssd/
image: https://wp-archive.baka.li/2020/12/Sandisk-SSD-Benchmrak.png
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 1584
views:
  - 872
categories:
  - it
tags:
  - SSD

---

## SSD

这是一块 2014 年 8 月购买的 [闪迪 至尊高速 128GB SSD][1] ，它从我的主力机上退役到群晖 NAS 上作系统盘使用，陆陆续续服役了 15306 小时。作为一块 MLC 颗粒的 SSD，我是准备把它当作传家宝一直用下去的。

直到有一次在查看 S.M.A.R.T. 的时候，惊讶的发现它已经对闪存写入了 230 TB 的数据。这对一块正常使用的 SSD 来说简直不可思议，什么概念？即使我每天重装一遍系统，写入 20GB 数据，也要接近四年才能写入这么多。

那么到底是怎么回事！

<img decoding="async" src="https://wp-archive.baka.li/2020/12/Sandisk-128GB-SSD.jpg" alt="" /> 

## S.M.A.R.T.

这块盘的 SMART 信息显示，对 SSD 的写入量为 40 TB，对 NAND 闪存的写入量是 230TB ，查了下资料说是因为写入放大导致的，罪魁祸首是 SSD 的主控。

<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    <strong>写入放大</strong>（英语：Write amplification，简称<strong>WA</strong>）是<a href="https://zh.wikipedia.org/wiki/%E9%97%AA%E5%AD%98">闪存</a>和<a href="https://zh.wikipedia.org/wiki/%E5%9B%BA%E6%80%81%E7%A1%AC%E7%9B%98">固态硬盘</a>（SSD）中一种不良的现象，即实际写入的物理资料量是写入资料量的多倍。
  </p>
  
  <cite>Wikipedia</cite>
</blockquote>

<img loading="lazy" decoding="async" width="648" height="190" src="https://wp-archive.baka.li/2020/12/Sandisk-128GB-SSD-NAND-Writes.jpg" alt="" class="wp-image-5811" srcset="https://wp-archive.baka.li/2020/12/Sandisk-128GB-SSD-NAND-Writes.jpg 648w, https://wp-archive.baka.li/2020/12/Sandisk-128GB-SSD-NAND-Writes-300x88.jpg 300w, https://wp-archive.baka.li/2020/12/Sandisk-128GB-SSD-NAND-Writes-150x44.jpg 150w" sizes="(max-width: 648px) 100vw, 648px" />  

这样只能淘汰掉这块硬盘，再给 NAS 换上新的 KIOXIA TC10 SSD 时那块 SSD 写入量已经到了 240TB &#8230;

拆下的 SSD 放到电脑上看看吧，CrystalDiskInfo 显示还有 39% 健康度，不愧是 MLC 颗粒。按照 3000PE 的寿命算，还能再写 140 TB，但是这写入放大系数我是不敢再用了。

[<img loading="lazy" decoding="async" width="1002" height="657" src="https://wp-archive.baka.li/2020/12/Sandisk-info.png" alt="" class="wp-image-5814" srcset="https://wp-archive.baka.li/2020/12/Sandisk-info.png 1002w, https://wp-archive.baka.li/2020/12/Sandisk-info-300x197.png 300w, https://wp-archive.baka.li/2020/12/Sandisk-info-150x98.png 150w, https://wp-archive.baka.li/2020/12/Sandisk-info-768x504.png 768w" sizes="(max-width: 1002px) 100vw, 1002px" />][2] 

## 跑个分

测速看下，读取速度没问题，写入速度直接暴跌到 50MB/s ，还不如很多古董机械硬盘。

<img loading="lazy" decoding="async" width="1002" height="552" src="https://wp-archive.baka.li/2020/12/Sandisk-SSD-Benchmrak.png" alt="" class="wp-image-5813" srcset="https://wp-archive.baka.li/2020/12/Sandisk-SSD-Benchmrak.png 1002w, https://wp-archive.baka.li/2020/12/Sandisk-SSD-Benchmrak-300x165.png 300w, https://wp-archive.baka.li/2020/12/Sandisk-SSD-Benchmrak-150x83.png 150w, https://wp-archive.baka.li/2020/12/Sandisk-SSD-Benchmrak-768x423.png 768w" sizes="(max-width: 1002px) 100vw, 1002px" />  

联想到最近西数的 SN550 、SN750 等 SSD 产品的冷数据掉速问题，而 闪迪早就被西数收购了，不太建议购买 西数\闪迪 家的 SSD 产品。

最后说下我选的这块 KIOXIA TC10 ，它就是之前东芝的 TR200 ，又名特弱 200 ，缓外写入速度不到 200 MB/s ，实属大号 U盘 。

但是它的 480GB 版本都是 东芝 96 层 3D TLC 颗粒的（至少我买到是），算是 TLC 颗粒里面比较好的，寿命有保障，而且价格不到 300 元，算是这价位的好选择。

 [1]: https://baka.li/sandisk-128gb-ssd/
 [2]: https://wp-archive.baka.li/2020/12/Sandisk-info.png