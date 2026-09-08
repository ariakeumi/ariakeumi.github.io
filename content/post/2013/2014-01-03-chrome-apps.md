---
title: 玩转Chrome第三弹 ～ 制作属于自己Chrome应用
author: 炒土豆丝
type: post
date: 2014-01-02T17:17:55+00:00
url: /chrome-apps/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 2030
dsq_thread_id:
  - 4547167247
views:
  - 685
categories:
  - it
tags:
  - Chrome

---
<address>
  <a class="lightbox" href="https://wp-archive.baka.li/2014/01/chrome-apps.jpg"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1167" src="https://wp-archive.baka.li/2014/01/chrome-apps.jpg" alt="chrome-apps" width="961" height="594" srcset="https://wp-archive.baka.li/2014/01/chrome-apps.jpg 961w, https://wp-archive.baka.li/2014/01/chrome-apps-300x185.jpg 300w" sizes="(max-width: 961px) 100vw, 961px" /></a>
</address>

Chrome上很多应用都是像书签一样，点击图标就是一个链接。

而制作这样一个应用是非常简单的，任何人都可以动手制作。

下面屋主我试着做一个打开自己部落格的Chrome应用。

首先，新建一个文件夹，在文件夹里面再新建一个文本。

拷贝以下代码，汉字部分自行替换成自己需要的。

<pre class="lang:js decode:true  ">{
"manifest_version": 2,
"name": "应用名字",
"description": "应用介绍",
"version": "1.1",
"icons": {
"128": "128.png"
},
"app": {
"urls": [
"http://替换上需要的链接.com/"
],
"launch": {
"web_url": "http://替换上需要的链接.com/"
}
},
"permissions": [
"unlimitedStorage",
"notifications"
]
}</pre>

这是我改好了的代码，可以用记事本保存为 manifest.json ，注意，必须是UTF-8编码的。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1099" src="https://wp-archive.baka.li/2013/12/manifest.json_.png" alt="manifest.json" width="837" height="645" srcset="https://wp-archive.baka.li/2013/12/manifest.json_.png 837w, https://wp-archive.baka.li/2013/12/manifest.json_-300x231.png 300w, https://wp-archive.baka.li/2013/12/manifest.json_-194x150.png 194w" sizes="(max-width: 837px) 100vw, 837px" />][1]

然后再制作一个128×128像素的图标，PNG格式的，命名为128.png，和manifest.json放在同一个文件夹。

Chrome地址栏输入 <chrome://extensions/> 进入扩展程序界面，在开发者模式的框框上打钩。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1100" src="https://wp-archive.baka.li/2013/12/kaifazhemoshi.png" alt="kaifazhemoshi" width="787" height="113" srcset="https://wp-archive.baka.li/2013/12/kaifazhemoshi.png 787w, https://wp-archive.baka.li/2013/12/kaifazhemoshi-300x43.png 300w" sizes="(max-width: 787px) 100vw, 787px" />][2]

接着点 加载正在开发的扩展程序 ，路径选存放manifest.json和图标的文件夹。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1101" src="https://wp-archive.baka.li/2013/12/bakatd-app.png" alt="bakatd-app" width="765" height="208" srcset="https://wp-archive.baka.li/2013/12/bakatd-app.png 765w, https://wp-archive.baka.li/2013/12/bakatd-app-300x81.png 300w" sizes="(max-width: 765px) 100vw, 765px" />][3]

这样一个Chrome应用就制作完成了，为了方便储存，还有将应用打包成CRX。

点击 打包扩展程序 ，路径依旧选择存放manifest.json和图标的文件夹。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1103" src="https://wp-archive.baka.li/2013/12/bakatd-app-2.png" alt="bakatd-app-2" width="519" height="216" srcset="https://wp-archive.baka.li/2013/12/bakatd-app-2.png 519w, https://wp-archive.baka.li/2013/12/bakatd-app-2-300x124.png 300w" sizes="(max-width: 519px) 100vw, 519px" />][4]

完成会产生一个CRX和PEM文件，CRX是本体，PEM是私钥，对我们来说没什么用。

把CRX文件拖拽入扩展程序界面（<chrome://extensions/>），出现这个窗口就说明成功了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1104" src="https://wp-archive.baka.li/2013/12/bakatd-app-3.png" alt="bakatd-app-3" width="386" height="201" srcset="https://wp-archive.baka.li/2013/12/bakatd-app-3.png 386w, https://wp-archive.baka.li/2013/12/bakatd-app-3-300x156.png 300w" sizes="(max-width: 386px) 100vw, 386px" />][5]

如果你有钱，甚至可以把这个应用发布到<a href="https://chrome.google.com/webstore/category/home" target="_blank" rel="noopener">Chrome应用商店</a>。

在<a href="https://chrome.google.com/webstore/developer/dashboard" target="_blank" rel="noopener">Chrome开发者信息中心</a>上传，需要5美刀 (ノ‥)ノ‥‥〓〓〓〓☆ピーーーー

最后，推荐个程序，<a title="点击下载Chrome应用启动器" href="https://chrome.google.com/webstore/launcher" target="_blank" rel="noopener">Chrome应用启动器</a>。

固定于任务栏，能很方便的打开和搜索东西。

[<img loading="lazy" decoding="async" class="alignnone size-medium wp-image-1105" src="https://wp-archive.baka.li/2013/12/Chrome-launcher.png" alt="Chrome-launcher" width="235" height="300" srcset="https://wp-archive.baka.li/2013/12/Chrome-launcher.png 394w, https://wp-archive.baka.li/2013/12/Chrome-launcher-235x300.png 235w" sizes="(max-width: 235px) 100vw, 235px" />][6]

<span style="color: #99cc00;"><a href="https://support.google.com/chrome/a/answer/2714278?hl=zh-Hans" target="_blank" rel="noopener"><span style="color: #99cc00;">官方文档：Chrome for Business和Chrome for Education &#8211; 创建 Chrome 应用</span></a></span>

 [1]: https://wp-archive.baka.li/2013/12/manifest.json_.png
 [2]: https://wp-archive.baka.li/2013/12/kaifazhemoshi.png
 [3]: https://wp-archive.baka.li/2013/12/bakatd-app.png
 [4]: https://wp-archive.baka.li/2013/12/bakatd-app-2.png
 [5]: https://wp-archive.baka.li/2013/12/bakatd-app-3.png
 [6]: https://wp-archive.baka.li/2013/12/Chrome-launcher.png