---
title: 让 Windows 系统支持显示 Emoji 表情的国旗
author: 炒土豆丝
type: post
date: 2022-11-27T19:24:58+00:00
url: /windows-emoji-flags/
image: https://wp-archive.baka.li/2022/11/emoji-flag-clash-yacd.webp
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - 'false'
argon_show_post_outdated_info:
  - default
views:
  - 821
categories:
  - app
tags:
  - Windows 软件

---
 

从 Win8 开始的新系统都支持显示 Emoji 表情，但因为政治原因，微软阉割了 Emoji 的国旗图像，在 Windows 系统里的国旗 Emoji 会显示为英文字符。

如果平时和 Emoji 国旗不打交道没什么影响，不过偏偏我常用的科学上网软件 Clash 的 yacd 控制面需要显示节点的国旗，他在 Windows 上显示是这样的：

<img loading="lazy" decoding="async" width="1305" height="741" src="https://wp-archive.baka.li/2022/11/clash-yacd.png" alt="" class="wp-image-6298" />  

很难看，实在是无法接受，虽然可以给节点名称去掉国旗，但一堆没国旗的节点名挤在一起也相当混乱。

然后我在 Github 上翻到了这个， <a rel="noreferrer noopener" href="https://github.com/13rac1/twemoji-color-font" target="_blank">Twitter Color Emoji SVGinOT Font</a> ，可以把 Windows 的原生 Emoji 表情替换为 Twitter 的 Emoji ，推特的 Emoji 是包含了国旗的。

安装方法很简单，下载 <a rel="noreferrer noopener" href="https://github.com/13rac1/twemoji-color-font/releases" target="_blank">TwitterColorEmoji-SVGinOT-Win-14.0.2.zip</a> 解压，运行 .bat 文件，会自动下载两个字体文件，然后直接安装字体就搞定了。

装完发现因为 <a rel="noreferrer noopener" href="https://bugs.chromium.org/p/chromium/issues/detail?id=306078" target="_blank">操作系统或者应用程序的限制</a> 不支持 Chrome，一大堆 Electron 的软件也不支持。

还好我常用的文本编辑器 Notepad3 是支持的，编辑 Clash 配置文件的时候很直观。

<img loading="lazy" decoding="async" width="1056" height="741" src="https://wp-archive.baka.li/2022/11/emoji-flag-notepad3.png" alt="" class="wp-image-6300" />  

然后我找到了 <a rel="noreferrer noopener" href="https://chrome.google.com/webstore/detail/twemoji-for-chrome/fopgafjdjlongoeblobbafbnapafcicg" target="_blank">Twemoji for Chrome</a> 这款 Chrome 插件，直接秒杀，完美显示 Emoji 国旗。

<img loading="lazy" decoding="async" width="1368" height="878" src="https://wp-archive.baka.li/2022/11/emoji-flag-clash-yacd.png" alt="" class="wp-image-6301" />  

[][1]

 [1]: https://emojipedia.org/zh/%E6%97%97-%E4%BC%8A%E6%9C%97/