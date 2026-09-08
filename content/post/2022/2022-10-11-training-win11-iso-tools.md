---
title: 制作绕过 TPM 检测的 Windows 11 系统安装镜像
author: 炒土豆丝
type: post
date: 2022-10-10T17:47:42+00:00
url: /training-win11-iso-tools/
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 600
categories:
  - app
tags:
  - Windows

---
微软给最新的 Windows 11 系统的安装上做了些限制，如果你的电脑配置过低或者不支持 TPM2.0 （可信平台模块），那你将无法继续安装。

我们可以用 <a rel="noreferrer noopener" href="https://www.heu8.net/" target="_blank">知己而知彼</a> 开发的 Training Win11 ISO Tools 工具制作绕过 TPM 检测和微软账号在线登录 Win11 系统安装镜像。

只需要把安装镜像放在工具目录里的 Source_ISO 目录，再运行 .bat 脚本就可以生成绕过 TPM 检测的 Windows 11 系统安装镜像了。

<img loading="lazy" decoding="async" width="952" height="628" src="https://wp-archive.baka.li/2022/10/Training_Win11_ISO_Tools.png" alt="" class="wp-image-6200" />  

下载：

## <a href="https://1drv.ms/u/s!Agj1VU8aYuuBgeYrwa7OVleVruUeiQ?e=g0ifp5" target="_blank" rel="noreferrer noopener">Training Win11 ISO Tools</a> 