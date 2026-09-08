---
title: 玩转Google Chrome第二弹 ～ 打包Chrome扩展程序到本地
author: 炒土豆丝
type: post
date: 2013-12-29T18:58:42+00:00
url: /chrome-extensions-unpack/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 1673
dsq_thread_id:
  - 4547167730
views:
  - 636
categories:
  - it
tags:
  - Chrome

---
<address>
  <a class="lightbox" href="https://wp-archive.baka.li/2013/12/chrome-extensions-unpack.jpg"><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1084" src="https://wp-archive.baka.li/2013/12/chrome-extensions-unpack.jpg" alt="chrome-extensions-unpack" width="1024" height="630" srcset="https://wp-archive.baka.li/2013/12/chrome-extensions-unpack.jpg 1024w, https://wp-archive.baka.li/2013/12/chrome-extensions-unpack-300x184.jpg 300w" sizes="(max-width: 1024px) 100vw, 1024px" /></a>
</address>

Chrome的同步功能非常强大，扩展什么的自然不在话下。

但有时候Google会清理<a title="Chrome应用商店" href="https://chrome.google.com/webstore/category/home" target="_blank" rel="noopener">Chrome应用商店</a>的扩展，虽然清理后扩展依旧会继续同步。

如果想要把扩展分享给别人就不行了。

所以这次来介绍如何打包扩展程序，非常的简单。

首先，地址栏输入 <a href="chrome://extensions/" target="_blank" rel="noopener">chrome://extensions/</a> 回车，到达扩展程序设置页面。

在右上角的开发者模式上打勾。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1078" src="https://wp-archive.baka.li/2013/12/chrome-extensions-developer.png" alt="chrome-extensions-developer" width="751" height="114" srcset="https://wp-archive.baka.li/2013/12/chrome-extensions-developer.png 751w, https://wp-archive.baka.li/2013/12/chrome-extensions-developer-300x45.png 300w" sizes="(max-width: 751px) 100vw, 751px" />][1]

以<a href="https://chrome.google.com/webstore/detail/adblock/gighmmpiobklfepjocnamgkkbiglidom" target="_blank" rel="noopener">Adblock</a>为例，拷贝它的ID。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1079" src="https://wp-archive.baka.li/2013/12/Adblock-extensions.png" alt="Adblock-extensions" width="751" height="179" srcset="https://wp-archive.baka.li/2013/12/Adblock-extensions.png 751w, https://wp-archive.baka.li/2013/12/Adblock-extensions-300x71.png 300w" sizes="(max-width: 751px) 100vw, 751px" />][2]

[syntax type=&#8221;html|php|js|css&#8221;]C:\Users\%username%\AppData\Local\Google\Chrome\User Data\Default\Extensions\extensions-ID[/syntax]

把“extensions-ID” 替换成要打包的程序的ID，如：

[syntax type=&#8221;html|php|js|css&#8221;]C:\Users\%username%\AppData\Local\Google\Chrome\User Data\Default\Extensions\gighmmpiobklfepjocnamgkkbiglidom[/syntax]

拷贝地址到地址栏打开，打开后就是一个版本号，把这个文件夹拷贝到其他地方，如桌面。

这是Chrome默认安装路径的扩展程序路径，如果安装在其他地方请自行修改。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1080" src="https://wp-archive.baka.li/2013/12/dakaihou.png" alt="dakaihou" width="634" height="133" srcset="https://wp-archive.baka.li/2013/12/dakaihou.png 634w, https://wp-archive.baka.li/2013/12/dakaihou-300x62.png 300w" sizes="(max-width: 634px) 100vw, 634px" />][3]

点击开发者模式的打包扩展程序，选择刚才拷贝出来的文件夹，打包可以了。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1081" src="https://wp-archive.baka.li/2013/12/extensions-unpack.png" alt="extensions-unpack" width="583" height="199" srcset="https://wp-archive.baka.li/2013/12/extensions-unpack.png 583w, https://wp-archive.baka.li/2013/12/extensions-unpack-300x102.png 300w" sizes="(max-width: 583px) 100vw, 583px" />][4]

打包完成后能看到一个CRX后辍的，这个就是打包好了的扩展程序，还有PEM后辍的，这个是私钥，不需要。

最后测试下打包好的扩展程序吧。

把CRX拖拽进Chrome的扩展程序设置页面（必须拽入这个页面，不然提示无法添加）。

成功了，是不是很简单！～

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-1082" src="https://wp-archive.baka.li/2013/12/Adblock-unpack.png" alt="Adblock-unpack" width="387" height="228" srcset="https://wp-archive.baka.li/2013/12/Adblock-unpack.png 387w, https://wp-archive.baka.li/2013/12/Adblock-unpack-300x176.png 300w" sizes="(max-width: 387px) 100vw, 387px" />][5]

 [1]: https://wp-archive.baka.li/2013/12/chrome-extensions-developer.png
 [2]: https://wp-archive.baka.li/2013/12/Adblock-extensions.png
 [3]: https://wp-archive.baka.li/2013/12/dakaihou.png
 [4]: https://wp-archive.baka.li/2013/12/extensions-unpack.png
 [5]: https://wp-archive.baka.li/2013/12/Adblock-unpack.png