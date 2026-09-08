---
title: Win7下实现自动拨号联网！~。。。
author: 炒土豆丝
type: post
date: 2013-01-29T16:00:00+00:00
url: /win7-auto-pppoe/
blogger_blog:
  - q000q000.blogspot.com
blogger_permalink:
  - /2013/01/win7.html
blogger_author:
  - 炒土豆丝
wpb_post_views_count:
  - 2411
views:
  - 798
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - app

---
因为没装Win7，所以这里就拿Win8来演示！

<div>
  <span style="font-family: Tahoma; text-align: -webkit-auto;">首先 Win +R运行 regedit</span>
</div>

<div>
</div>

<div>
  <img loading="lazy" decoding="async" class="alignnone size-medium" src="http://3.bp.blogspot.com/-26zGyQMZfy4/UQjQynt5TPI/AAAAAAAAAA8/unrFGBaeU_I/s1600/QQ%E6%88%AA%E5%9B%BE20130130154853.png" width="413" height="213" />
</div>

<div>
  <span style="font-family: Tahoma; text-align: -webkit-auto;"> </span>
</div>

这样就打开了注册表编辑器。

<img loading="lazy" decoding="async" class="alignnone size-medium" src="http://3.bp.blogspot.com/-K9rlkdjganA/UQjRL4xinFI/AAAAAAAAABE/B0wA3PaqU3Y/s1600/QQ%E6%88%AA%E5%9B%BE20130130154431.png" width="465" height="275" /> 

找到路径 <span style="font-family: Tahoma; text-align: -webkit-auto;">HKEY_LOCAL_MACHINESOFTWAREMicrosoftWindowsCurrentVersionRun</span>

<img loading="lazy" decoding="async" class="alignnone size-medium" src="https://1.bp.blogspot.com/-3ukIyT8o038/UQjRNaog5PI/AAAAAAAAABM/R_LfPQH0ASw/s1600/QQ%E6%88%AA%E5%9B%BE20130130154634.png" width="788" height="325" /> 

<div>
  <span style="font-family: Tahoma; text-align: -webkit-auto;">然后 创建字符串值 （名称随便），输入键值为 </span><span style="font-family: Tahoma; text-align: -webkit-auto;">C:windowssystem32rasphone.exe -d 宽带连接 </span>
</div>

<div>
</div>

<div>
  <img loading="lazy" decoding="async" class="alignnone size-medium" src="http://3.bp.blogspot.com/-WMwqngSaOP4/UQjRN6zS2DI/AAAAAAAAABU/3hJ7UAN5ILE/s1600/QQ%E6%88%AA%E5%9B%BE20130130154717.png" width="788" height="322" />
</div>

<div>
</div>

<div class="separator" style="clear: both; text-align: center;">
</div>

<div class="separator" style="clear: both; text-align: center;">
  这样就基本大功告成了，如果你开机的时候不想看到弹出的网络连接窗口，
</div>

<div class="separator" style="clear: both; text-align: center;">
  可以<span style="background-color: white; color: #444444; font-family: 微软雅黑, Tahoma, 'Microsoft Yahei', Simsun; font-size: 15.333333015441895px; line-height: 14.666666984558105px;">右击宽带连接名称，属性选择 不显示 拨号框等！~</span>
</div>

<div>
</div>

<div class="separator" style="clear: both; text-align: center;">
</div>

<div>
  <img loading="lazy" decoding="async" class="alignnone size-medium" src="http://1.bp.blogspot.com/-UY9POsOR9A0/UQjS3wbQSYI/AAAAAAAAABk/oXwn-Ye9HtM/s1600/214252gcgvlem7lllzcg3v.jpg" width="377" height="426" />
</div>

<div class="separator" style="clear: both; text-align: center;">
  <span style="background-color: white; color: #444444; font-family: 微软雅黑, Tahoma, 'Microsoft Yahei', Simsun; font-size: 15.333333015441895px; line-height: 14.666666984558105px;"> </span>
</div>

<div class="separator" style="clear: both; text-align: center;">
</div>

<div class="separator" style="clear: both; text-align: center;">
</div>

<div class="separator" style="clear: both; text-align: center;">
</div>

<div class="separator" style="clear: both; text-align: center;">
</div>