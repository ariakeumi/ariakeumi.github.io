---
title: 抛弃 AdGuard Home , 直接使用 OpenClash 过滤广告 , OpenWrt 路由器过滤广告最简单的方法！
author: 炒土豆丝
type: post
date: 2024-03-31T02:49:00+00:00
url: /openclash-adblock/
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
views:
  - 47
categories:
  - app
tags:
  - 科学上网
  - 路由器
  - OpenWrt

---
## 前言 

在路由器上进行广告过滤可以帮助我在不方便安装广告过滤软件的设备上过滤掉一些简单的广告。

我尝试过很多在路由器上过滤广告的方法，最早使用的是 Adbyby ，但它多年没有维护，不能运行在较新的 OpenWrt 固件上了。

## 抛弃 AdGuard Home  

后来换 AdGuard Home 来过滤广告，ADG 有着好看易用的 WEB 界面，经过少许麻烦的配置就可以使用，参考 [红米 AX6000 路由器配置 AdGuard Home + OpenClash][1] 这篇文章，使用后期遇到了斗鱼弹幕无法加载的问题，尝试了各种方法都无法解决。

还有类似的 Pi-hole 这样的软件，和 OpenClash 搭配似乎都会遇到些麻烦。

## 使用 OpenClash 去广告 

开始熟悉 OpenClash 后，我在 Clash 的配置文件里加入广告过滤规则，能获得和 AdGuard Home 差不多的过滤效果。

最重要的是我的网络拓扑变得非常简单，出现问题很容易排查，事实上换了这套方案网络一直很稳定。

如果你也使用 OpenClash 来进行科学上网，那直接用它来过滤广告最合适不过了。

## 配置 OpenClash  

OpenClash 我使用了 **Meta 内核** ，**Redir-Host 兼容模式** 运行，开启了 **仅允许常用端口流量** ，不要开启 绕过中国大陆 IP ，这样就无法过滤国内的广告了。

Clash 配置文件里插入下面的广告过滤规则：

```
proxies:

proxy-groups:
  - name: 🛑 广告拦截
    type: select
    proxies:
      - REJECT
      - DIRECT

rule-providers: 
  秋风广告规则:
    type: http
    behavior: domain
    format: yaml
    path: ./rule_providers/AWAvenue-Ads-Rule-Clash.yaml
    url: "https://mirror.ghproxy.com/https://raw.githubusercontent.com/TG-Twilight/AWAvenue-Ads-Rule/main/Filters/AWAvenue-Ads-Rule-Clash.yaml"
    interval: 60480
    
  BanAD:
    type: http
    behavior: classical
    url: "https://raw.staticdn.net/ACL4SSR/ACL4SSR/master/Clash/Providers/BanAD.yaml"
    path: ./ACL4SSR/BanAD.yaml
    interval: 86400
    
  BanEasyList:
    type: http
    behavior: classical
    url: "https://raw.staticdn.net/ACL4SSR/ACL4SSR/master/Clash/Providers/BanEasyList.yaml"
    path: ./ACL4SSR/BanEasyList.yaml
    interval: 86400
    
  BanEasyListChina:
    type: http
    behavior: classical
    url: "https://raw.staticdn.net/ACL4SSR/ACL4SSR/master/Clash/Providers/BanEasyListChina.yaml"
    path: ./ACL4SSR/BanEasyListChina.yaml
    interval: 86400
    
  BanEasyPrivacy:
    type: http
    behavior: classical
    url: "https://raw.staticdn.net/ACL4SSR/ACL4SSR/master/Clash/Providers/BanEasyPrivacy.yaml"
    path: ./ACL4SSR/BanEasyPrivacy.yaml
    interval: 86400
    
  BanProgramAD:
    type: http
    behavior: classical
    url: "https://raw.staticdn.net/ACL4SSR/ACL4SSR/master/Clash/Providers/BanProgramAD.yaml"
    path: ./ACL4SSR/BanProgramAD.yaml
    interval: 86400

rules:
  - RULE-SET,秋风广告规则,🛑 广告拦截
  - RULE-SET,BanAD,🛑 广告拦截
  - RULE-SET,BanEasyList,🛑 广告拦截
  - RULE-SET,BanEasyListChina,🛑 广告拦截
  - RULE-SET,BanEasyPrivacy,🛑 广告拦截
  - RULE-SET,BanProgramAD,🛑 广告拦截

```

加起来接近七万条广告过滤规则，在 yacd 面板里可以手动更新规则而不重启 OpenClash ，过滤出现问题也可以把 🛑 广告拦截 改成 DIRECT 临时暂停过滤。

![yacd面板](https://wp-archive.baka.li/2024/03/clash-adb-rules.png)

## 缺点

因为过滤规则太多，加上国内流量也通过 Clash 内核，CPU 性能太弱的路由器跑起来可能会很吃力。

我的 红米 AX6000 跑起来毫无压力，x86 软路由应该也没问题。

另外此类过滤方法基本无法过滤视频广告，桌面用户还是得配合 uBlock Origin 等浏览器插件使用。

