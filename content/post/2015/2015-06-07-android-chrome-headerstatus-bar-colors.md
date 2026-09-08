---
title: Android Lollipop ：Chrome地址栏
author: 炒土豆丝
type: post
date: 2015-06-06T21:26:48+00:00
url: /android-chrome-headerstatus-bar-colors/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 1410
dsq_thread_id:
  - 6169388859
views:
  - 699
categories:
  - it
tags:
  - Android
  - Android APP

---
在 Android 5.0 Lollipop 中，Chrome 浏览器 V39 增加地址栏/地址栏的调色功能。

只需要在 WordPress 下只要在主题中的 Header.php 文件添加一行这样的代码：

> <meta name=&#8221;theme-color&#8221; content=&#8221;#Hex颜色代码&#8221;>

一般地址栏/状态栏要和自己的网站主题颜色搭配比较好看，所以先用 Chrome 拾色，按 Ctrl + Shift + J 进入控制台，选取需要的颜色，得到 RGB 颜色代码。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4089" src="https://wp-archive.baka.li/2015/06/css-rgb.png" alt="css-rgb" width="1136" height="739" srcset="https://wp-archive.baka.li/2015/06/css-rgb.png 1136w, https://wp-archive.baka.li/2015/06/css-rgb-150x98.png 150w, https://wp-archive.baka.li/2015/06/css-rgb-300x195.png 300w, https://wp-archive.baka.li/2015/06/css-rgb-1024x666.png 1024w" sizes="(max-width: 1136px) 100vw, 1136px" />][1]

把 RGB 代码（41,111,163）转为 Hex 代码，得到 293fa3 。

## <a href="http://www.javascripter.net/faq/rgbtohex.htm" target="_blank" rel="noopener">在线 RGB 转 Hex</a>

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4090" src="https://wp-archive.baka.li/2015/06/RGB-to-hex.png" alt="RGB-to-hex" width="630" height="316" srcset="https://wp-archive.baka.li/2015/06/RGB-to-hex.png 630w, https://wp-archive.baka.li/2015/06/RGB-to-hex-150x75.png 150w, https://wp-archive.baka.li/2015/06/RGB-to-hex-300x150.png 300w" sizes="(max-width: 630px) 100vw, 630px" />][2]

添加到 Header.php 。

> <meta name=&#8221;theme-color&#8221; content=&#8221;#293fa3&#8243;>

Done ，色彩斑斓的 Lollipop！

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4091" src="https://wp-archive.baka.li/2015/06/android-chrome-bakahouse.jpg" alt="android-chrome-bakahouse" width="405" height="720" srcset="https://wp-archive.baka.li/2015/06/android-chrome-bakahouse.jpg 405w, https://wp-archive.baka.li/2015/06/android-chrome-bakahouse-84x150.jpg 84w, https://wp-archive.baka.li/2015/06/android-chrome-bakahouse-169x300.jpg 169w" sizes="(max-width: 405px) 100vw, 405px" />][3] [<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4092" src="https://wp-archive.baka.li/2015/06/android-chrome-Colors-bar.jpg" alt="android-chrome-Colors-bar" width="405" height="720" srcset="https://wp-archive.baka.li/2015/06/android-chrome-Colors-bar.jpg 405w, https://wp-archive.baka.li/2015/06/android-chrome-Colors-bar-84x150.jpg 84w, https://wp-archive.baka.li/2015/06/android-chrome-Colors-bar-169x300.jpg 169w" sizes="(max-width: 405px) 100vw, 405px" />][4]

 [1]: https://wp-archive.baka.li/2015/06/css-rgb.png
 [2]: https://wp-archive.baka.li/2015/06/RGB-to-hex.png
 [3]: https://wp-archive.baka.li/2015/06/android-chrome-bakahouse.jpg
 [4]: https://wp-archive.baka.li/2015/06/android-chrome-Colors-bar.jpg