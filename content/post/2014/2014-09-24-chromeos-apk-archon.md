---
title: ARChon:使用Chrome运行Android APP
author: 炒土豆丝
type: post
date: 2014-09-23T20:23:58+00:00
url: /chromeos-apk-archon/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 5099
dsq_thread_id:
  - 3975479008
views:
  - 757
categories:
  - app
tags:
  - Chrome

---
[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-2996" src="https://wp-archive.baka.li/2014/09/chromeos-apk.png" alt="chromeos-apk" width="1600" height="1024" srcset="https://wp-archive.baka.li/2014/09/chromeos-apk.png 1600w, https://wp-archive.baka.li/2014/09/chromeos-apk-150x96.png 150w, https://wp-archive.baka.li/2014/09/chromeos-apk-300x192.png 300w, https://wp-archive.baka.li/2014/09/chromeos-apk-1024x655.png 1024w" sizes="(max-width: 1600px) 100vw, 1600px" />][1]

> ARChon提供了一个修改版的ARC，因此能够以扩展的形式安装到Chrome浏览器上，并且无关于用户所使用的平台。如此一来，我们就可以全平台畅玩Android app了！

首先，此方法需要Chrome 37或以上版本。

然后下载对应的运行环境文件。

| Runtime                                                                                            | Download                                                          |
| -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| ARChon 1.0 &#8211; Intel x86 64-bit                                                                | [BitBucket][2]MD5:3bd2e6014a0cba0b1ee3c69462a9b46d                |
| ARChon 1.1 &#8211; Intel x86 **Chrome 64-bit / Chrome OS 64-bit** (OSX: Use this in Chrome Canary) | [BitBucket][3] :: [GitHub][4]MD5:d409801cac97cdff9ea6aad468ddc927 |
| ARChon 1.1 &#8211; Intel x86 **Chrome 32-bit / Chrome OS 32-bit** (OSX: Use this in Chrome Stable) | [BitBucket][5] :: [GitHub][6]MD5:873c4d116eabd1a5ebedec65d11d6d8a |
| ARChon 1.1 &#8211; ARM (i.e ARM-based Chromebooks)                                                 | [BitBucket][7] :: [GitHub][8]MD5:d0a69d822399545ff67292b50f8c4047 |

下载后解压，然后以开发者模式 &#8211; 加载正在开发的扩展，选择刚才解压后文件路径，提示警告，不用管。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-2997" src="https://wp-archive.baka.li/2014/09/Chromeos-apk-1.png" alt="Chromeos-apk-1" width="709" height="315" srcset="https://wp-archive.baka.li/2014/09/Chromeos-apk-1.png 709w, https://wp-archive.baka.li/2014/09/Chromeos-apk-1-150x66.png 150w, https://wp-archive.baka.li/2014/09/Chromeos-apk-1-300x133.png 300w" sizes="(max-width: 709px) 100vw, 709px" />][9]

接着下载一个叫<a title="下载" href="http://nodejs.org/download/" target="_blank">Node.js</a>（点击下载）的工具，用来把 Android 安装包的 APK 文件转换为 Chrome 的扩展程序文件，自行选择平台。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-2998" src="https://wp-archive.baka.li/2014/09/Chromeos-apk-2.png" alt="Chromeos-apk-2" width="659" height="383" srcset="https://wp-archive.baka.li/2014/09/Chromeos-apk-2.png 659w, https://wp-archive.baka.li/2014/09/Chromeos-apk-2-150x87.png 150w, https://wp-archive.baka.li/2014/09/Chromeos-apk-2-300x174.png 300w" sizes="(max-width: 659px) 100vw, 659px" />][10]

安装 Node.js ，打开 Node.js command prompt ，在命令行窗口中输入：

<pre class="lang:default decode:true ">npm install chromeos-apk -g</pre>

如下图，然后关闭窗口。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-2999" src="https://wp-archive.baka.li/2014/09/chromeos-apk-3.png" alt="chromeos-apk-3" width="677" height="443" srcset="https://wp-archive.baka.li/2014/09/chromeos-apk-3.png 677w, https://wp-archive.baka.li/2014/09/chromeos-apk-3-150x98.png 150w, https://wp-archive.baka.li/2014/09/chromeos-apk-3-300x196.png 300w" sizes="(max-width: 677px) 100vw, 677px" />][11]

再选择需要的APK，用下面的命令转换：

<pre class="lang:default decode:true ">chromeos-apk 安装包.apk</pre>

如果以要以横屏运行APP，运行下面命令：

<pre class="lang:default decode:true ">chromeos-apk 安装包.apk --tablet</pre>

在 Windows 下需要码上路径，如下图。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3000" src="https://wp-archive.baka.li/2014/09/chromeos-apk-4.png" alt="chromeos-apk-4" width="677" height="443" srcset="https://wp-archive.baka.li/2014/09/chromeos-apk-4.png 677w, https://wp-archive.baka.li/2014/09/chromeos-apk-4-150x98.png 150w, https://wp-archive.baka.li/2014/09/chromeos-apk-4-300x196.png 300w" sizes="(max-width: 677px) 100vw, 677px" />][12]

在 Windows 下，转换成功后的 APK 文件会在用户根目录下。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3001" src="https://wp-archive.baka.li/2014/09/chromeos-apk-5.png" alt="chromeos-apk-5" width="976" height="607" srcset="https://wp-archive.baka.li/2014/09/chromeos-apk-5.png 976w, https://wp-archive.baka.li/2014/09/chromeos-apk-5-150x93.png 150w, https://wp-archive.baka.li/2014/09/chromeos-apk-5-300x186.png 300w, https://wp-archive.baka.li/2014/09/chromeos-apk-5-400x250.png 400w" sizes="(max-width: 976px) 100vw, 976px" />][13]

再以开发者模式 &#8211; 加载正在开发的扩展 来加载刚才转换好的 APK ，这样就可以直接运行了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-3002" src="https://wp-archive.baka.li/2014/09/chromeos-apk-6.png" alt="chromeos-apk-6" width="1048" height="690" srcset="https://wp-archive.baka.li/2014/09/chromeos-apk-6.png 1048w, https://wp-archive.baka.li/2014/09/chromeos-apk-6-150x98.png 150w, https://wp-archive.baka.li/2014/09/chromeos-apk-6-300x197.png 300w, https://wp-archive.baka.li/2014/09/chromeos-apk-6-1024x674.png 1024w" sizes="(max-width: 1048px) 100vw, 1048px" />][14]

测试五个应用，只有两个能成功，一个是 <a href="http://coolapk.com/apk/com.twitter.android" target="_blank">推特</a> 官方客户端，另一个是 <a title="下载" href="http://coolapk.com/apk/com.mzba.happy.laugh" target="_blank">Smooth</a> 新浪微博客户端，暂时比较失望，而且很吃CPU。

不过这还是个很有前途的项目，在 Windows 下能调用系统输入法和资源管理器，运行很流畅，比 VM 等虚拟机里体验好很多，还能在linux和OS X上运行，只待成熟。

## 开发者：

## <a title="github" href="https://github.com/vladikoff/chromeos-apk/blob/master/archon.md" target="_blank">ARChon Custom Runtime Guide</a>

## 鸣谢：

## [正经事 • Chrome 运行 Android 应用！][15]

## <a href="https://github.com/fython/chromeos-apk" target="_blank">在Chrome上运行Android APKs (Chinese Edition, 仅翻译说明手册)</a>

 [1]: https://wp-archive.baka.li/2014/09/chromeos-apk.png
 [2]: https://bitbucket.org/vladikoff/archon/get/v1.0.zip
 [3]: https://bitbucket.org/vladikoff/archon/get/v1.1-x86_64.zip
 [4]: https://github.com/vladikoff/chromeos-apk/releases/download/v3.0.0/ARChon-v1.1-x86_64.zip
 [5]: https://bitbucket.org/vladikoff/archon/get/v1.1-x86_32.zip
 [6]: https://github.com/vladikoff/chromeos-apk/releases/download/v3.0.0/ARChon-v1.1-x86_32.zip
 [7]: https://bitbucket.org/vladikoff/archon/get/v1.1-ARM.zip
 [8]: https://github.com/vladikoff/chromeos-apk/releases/download/v3.0.0/ARChon-v1.1-ARM.zip
 [9]: https://wp-archive.baka.li/2014/09/Chromeos-apk-1.png
 [10]: https://wp-archive.baka.li/2014/09/Chromeos-apk-2.png
 [11]: https://wp-archive.baka.li/2014/09/chromeos-apk-3.png
 [12]: https://wp-archive.baka.li/2014/09/chromeos-apk-4.png
 [13]: https://wp-archive.baka.li/2014/09/chromeos-apk-5.png
 [14]: https://wp-archive.baka.li/2014/09/chromeos-apk-6.png
 [15]: http://micromacer.lofter.com/post/1c7abf_2677f57