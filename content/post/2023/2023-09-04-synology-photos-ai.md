---
title: 黑群晖开启 Synology Photos 的 AI 对象识别功能
author: 炒土豆丝
type: post
date: 2023-09-04T01:25:19+00:00
url: /synology-photos-ai/
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 398
categories:
  - app
tags:
  - NAS
  - 黑群晖

---
 

## 群晖相册 

<a href="https://www.synology.cn/zh-cn/dsm/feature/photos" target="_blank" rel="noreferrer noopener">Synology Photos</a> 是群晖系统的相册应用，他的前身 Memonts 应用有个对象识别功能，可以帮你自动分类相册，就像 Google Photos 那样。

在升级 DSM 7.0 后群晖砍了掉这个功能，近期又在 Synology Photos 1.5.0-0488 版本里更新了这个功能。

[<img loading="lazy" decoding="async" width="981" height="589" src="https://wp-archive.baka.li/2023/09/synologo-photos-ai.png" alt="" class="wp-image-6679" />][1] 

虽然识别错误不少，但是找猫图还是方便多了。

## 硬件要求 

黑群晖最常用的引导是 DS918+ 、DS920+ 和 DS3617xs 这几个型号，如果是 DS918+ 和 DS920+ 引导的黑群晖，需要最低 4GB 内存才能开启对象识别功能，而 DS3617xs 则需要 8GB 内存，白群晖也一样。

## 人脸识别补丁 

对象识别功能需要调用核显 GPU 来实现，如果是没有核显的黑群晖，需要打上人脸识别补丁，让它调用 CPU 来识别。

先停用 Synology Photos ，进 SSH 执行下面几行代码。

<pre class="wp-block-code"><code>wget http://code.imnks.com/face/PatchELFSharp
chmod +x PatchELFSharp
./PatchELFSharp "/var/packages/SynologyPhotos/target/usr/lib/libsynophoto-plugin-model.so.1.0" "_ZN9synophoto6plugin7network9IeNetwork11IsSupportedEv" "B8 00 00 00 00 C3"</code></pre>

重新启动 Synology Photos 后进设置勾选 ”在个人空间中启动主题相册“ ，再重建索引就行。

[<img loading="lazy" decoding="async" width="615" height="581" src="https://wp-archive.baka.li/2023/09/synologo-photos-set.png" alt="" class="wp-image-6680" />][2] 

人脸识别补丁来自 我不是矿神 博客：[黑群晖DSM7.0/7.1/7.2 Synology Photos人脸识别补丁][3]

 [1]: https://wp-archive.baka.li/2023/09/synologo-photos-ai.png
 [2]: https://wp-archive.baka.li/2023/09/synologo-photos-set.png
 [3]: https://imnks.com/4069.html