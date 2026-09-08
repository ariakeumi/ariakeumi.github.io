---
title: 挖坑：第三方设备接入苹果 Homekit 指南
author: 炒土豆丝
type: post
date: 2020-11-25T10:52:34+00:00
url: /mijia-to-homekit/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 3672
views:
  - 2550
categories:
  - it
tags:
  - Apple

---
<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    HomeKit是苹果公司推出的一个软件框架，它可以让用户使用苹果设备对智能家居电器进行配置、沟通和控制。通过在HomeKit服务中设计房间、物品和动作，用户可以通过对Siri的简单语音命令或通过家庭应用来实现家中的自动动作。&nbsp;
  </p>
  
  <cite><a href="https://zh.wikipedia.org/zh-cn/HomeKit" target="_blank" rel="noreferrer noopener">维基百科</a></cite>
</blockquote>

相信很多人已经购买了一些智能家居的产品，这方面国内做得最好的莫过于米家了，性价比高颜值不错，本人也购买了一些米家的产品。

既然选择了米家为什么不用 米家 APP 还要接入 Homekit 呢？那当然是米家 APP 不好用，当论功能米家其实比 Homekit 强，但是它的 APP 响应慢启动慢，布局不好，每个设备的操作逻辑都不统一，还经常改，甚至还有广告。

<img loading="lazy" decoding="async" width="591" height="1280" src="https://wp-archive.baka.li/2020/11/mijia-app.jpg" alt="" class="wp-image-5789" srcset="https://wp-archive.baka.li/2020/11/mijia-app.jpg 591w, https://wp-archive.baka.li/2020/11/mijia-app-139x300.jpg 139w, https://wp-archive.baka.li/2020/11/mijia-app-473x1024.jpg 473w, https://wp-archive.baka.li/2020/11/mijia-app-69x150.jpg 69w" sizes="(max-width: 591px) 100vw, 591px" />  

而苹果全家桶用户使用 家庭 APP ，你可以用 Siri 语音控制，或是在 Mac 、Apple TV 上控制。

<img loading="lazy" decoding="async" width="591" height="1280" src="https://wp-archive.baka.li/2020/11/ios-home-app.jpg" alt="" class="wp-image-5802" srcset="https://wp-archive.baka.li/2020/11/ios-home-app.jpg 591w, https://wp-archive.baka.li/2020/11/ios-home-app-139x300.jpg 139w, https://wp-archive.baka.li/2020/11/ios-home-app-473x1024.jpg 473w, https://wp-archive.baka.li/2020/11/ios-home-app-69x150.jpg 69w" sizes="(max-width: 591px) 100vw, 591px" />  

上面得种种原因让我决定放弃米家迁移到 Homekit 上。

米家或者绿米 Aqara的几乎所有基于 Zigbee 协议的设备（如各种传感器）都能通过支持 Homekit 的网关原生接入 Homekit ，就是下面三款，个人推荐 Aqara M1S，有扬声器可以报警。

<img loading="lazy" decoding="async" width="820" height="281" src="https://wp-archive.baka.li/2020/11/mijia-aqara-hub.png" alt="" class="wp-image-5791" srcset="https://wp-archive.baka.li/2020/11/mijia-aqara-hub.png 820w, https://wp-archive.baka.li/2020/11/mijia-aqara-hub-300x103.png 300w, https://wp-archive.baka.li/2020/11/mijia-aqara-hub-150x51.png 150w, https://wp-archive.baka.li/2020/11/mijia-aqara-hub-768x263.png 768w" sizes="(max-width: 820px) 100vw, 820px" />  

还有米家台灯 1S 也是米家为数不多原生接入 Homekit 的设备。

接下来就说原生不支持接入 Homekit ，但是可以通过 HomeBridge 桥接的设备：

  * 米家扫地机器人
  * 米家各种空气净化器
  * 米家和智米的各种风扇
  * 空调伴侣
  * 米家各种插座和插线板
  * 小佩宠物喂食器Mini

以上是我用过的或者是我知道的能通过 HomeBridge 桥接的设备。

那么除了能桥接到 Homekit 的智能设备，你还需要以下东西：

  * 一台 24 小时运行的群晖 NAS 或者树莓派之类的 Linux 设备
  * 一台作为家庭中枢的苹果设备，如 iPad 、HomePod 或者 Apple TV
  * 一点点的计算机基础知识

本人使用的是群晖 DS218+ ，通过 Docker 运行了 HomeBridge 、Home Assistant 、MQTT ，Home Assistant 和 MQTT 是为了让斐讯的 TC1 插排接入，过程过于繁琐而且需要用到编程器给插排刷固件就不细说了，其他设备都是通过 HomeBridge 接入的。

首先我们在群晖的套件中心里安装 Docker ，然后启动 Docker ，在注册表项搜索 HomeBridge ，下载 oznu/homebridge ，标签选择 latest 。

<img loading="lazy" decoding="async" width="1042" height="345" src="https://wp-archive.baka.li/2020/11/synology-docker.jpg" alt="" class="wp-image-5775" srcset="https://wp-archive.baka.li/2020/11/synology-docker.jpg 1042w, https://wp-archive.baka.li/2020/11/synology-docker-300x99.jpg 300w, https://wp-archive.baka.li/2020/11/synology-docker-1024x339.jpg 1024w, https://wp-archive.baka.li/2020/11/synology-docker-150x50.jpg 150w, https://wp-archive.baka.li/2020/11/synology-docker-768x254.jpg 768w" sizes="(max-width: 1042px) 100vw, 1042px" />  

下载完成后在 映像 里找到它启动，然后打开“高级设置”，在 “启用自动重新启动” 那里打勾。

接着在 “卷” 选项卡里点击 “添加文件夹” 。选择 Docker 目录，创建名为 “homebridge” 的目录，装载路径填 “/homebridge” 。

<img loading="lazy" decoding="async" width="644" height="542" src="https://wp-archive.baka.li/2020/11/docker-homebridge-folder.jpg" alt="" class="wp-image-5776" srcset="https://wp-archive.baka.li/2020/11/docker-homebridge-folder.jpg 644w, https://wp-archive.baka.li/2020/11/docker-homebridge-folder-300x252.jpg 300w, https://wp-archive.baka.li/2020/11/docker-homebridge-folder-150x126.jpg 150w" sizes="(max-width: 644px) 100vw, 644px" />  

端口设置选项卡里，勾选“使用与Docker Host 相同的网络”。

环境选项卡，新增变量“ DSM_HOSTNAME ” ，值那里填你的群晖 NAS 主机名。

再新增变量“PACKAGES” ，值填 “ffmpeg” 。

<img loading="lazy" decoding="async" width="639" height="564" src="https://wp-archive.baka.li/2020/11/docker-homebridge-folder-path.jpg" alt="" class="wp-image-5777" srcset="https://wp-archive.baka.li/2020/11/docker-homebridge-folder-path.jpg 639w, https://wp-archive.baka.li/2020/11/docker-homebridge-folder-path-300x265.jpg 300w, https://wp-archive.baka.li/2020/11/docker-homebridge-folder-path-150x132.jpg 150w" sizes="(max-width: 639px) 100vw, 639px" />  

点击应用就开始启动 HomeBridge 了，启动后选择容器，点击详情，再点击终端机，再点新增，输入 sh 后回车，在终端里输入以下命令安装 <a href="https://github.com/oznu/homebridge-config-ui-x" target="_blank" rel="noreferrer noopener">Homebridge Config UI X</a> 。

<pre class="wp-block-code"><code>npm install -g --unsafe-perm homebridge-config-ui-x</code></pre>

<img loading="lazy" decoding="async" width="855" height="437" src="https://wp-archive.baka.li/2020/11/docker-homebridge-sh.jpg" alt="" class="wp-image-5778" srcset="https://wp-archive.baka.li/2020/11/docker-homebridge-sh.jpg 855w, https://wp-archive.baka.li/2020/11/docker-homebridge-sh-300x153.jpg 300w, https://wp-archive.baka.li/2020/11/docker-homebridge-sh-150x77.jpg 150w, https://wp-archive.baka.li/2020/11/docker-homebridge-sh-768x393.jpg 768w" sizes="(max-width: 855px) 100vw, 855px" />  

安装完成后，在群晖的 File Station 里打开 docker/homebridge 目录，选择 config.json ，右键用文本编辑器打开，加入以下代码：

<pre class="wp-block-code"><code>"platforms": &#91;
    {
      "platform": "config",
      "name": "Config",
      "port": 8888,
      "sudo": false
    }
]</code></pre>

示例：

<img loading="lazy" decoding="async" width="895" height="471" src="https://wp-archive.baka.li/2020/11/docker-homebridge-config-ui-x.jpg" alt="" class="wp-image-5781" srcset="https://wp-archive.baka.li/2020/11/docker-homebridge-config-ui-x.jpg 895w, https://wp-archive.baka.li/2020/11/docker-homebridge-config-ui-x-300x158.jpg 300w, https://wp-archive.baka.li/2020/11/docker-homebridge-config-ui-x-150x79.jpg 150w, https://wp-archive.baka.li/2020/11/docker-homebridge-config-ui-x-768x404.jpg 768w" sizes="(max-width: 895px) 100vw, 895px" />  

再在 Docker 里面重启 Homebridge ，输入 NAS IP:8888 就可以进入 Homebridge 的 Web 界面了。

<img loading="lazy" decoding="async" width="1320" height="1038" src="https://wp-archive.baka.li/2020/11/homebridge-ui-x.jpg" alt="" class="wp-image-5785" srcset="https://wp-archive.baka.li/2020/11/homebridge-ui-x.jpg 1320w, https://wp-archive.baka.li/2020/11/homebridge-ui-x-300x236.jpg 300w, https://wp-archive.baka.li/2020/11/homebridge-ui-x-1024x805.jpg 1024w, https://wp-archive.baka.li/2020/11/homebridge-ui-x-150x118.jpg 150w, https://wp-archive.baka.li/2020/11/homebridge-ui-x-768x604.jpg 768w" sizes="(max-width: 1320px) 100vw, 1320px" />  

安装了 HomeBridge config UI X 后就可以很方便的在 WEB 界面安装各种插件。

下面来说说我所安装的插件。

<a rel="noreferrer noopener" href="http://Homebridge Petkit Feeder Mini" target="_blank">Homebridge Petkit Feeder Mini</a>

小佩宠物自动喂食器mini，可以控制投喂猫粮，还有猫粮没了会提醒。

<a rel="noreferrer noopener" href="https://github.com/merdok/homebridge-xiaomi-fan#readme" target="_blank">Homebridge Xiaomi Fan</a>

我用来控制米家1X风扇，米家智米的基本都支持。

<a rel="noreferrer noopener" href="https://github.com/YinHangCode/homebridge-mi-outlet" target="_blank">Homebridge Mi Outlet</a>

支持米家智能插座基础版、小米智能插座\_USB版、米家智能插线板、青米智能插线板\_五孔位版、青米智能插线板_USB版、米家智能插座增强版 。

<a rel="noreferrer noopener" href="https://github.com/Sunoo/homebridge-camera-ffmpeg#readme" target="_blank">Homebridge Camera FFmpeg</a>

支持 RTSP 推流的监控摄像头都能接入 Homekit ，但只能看预览实时画面，不能看回放。

<a rel="noreferrer noopener" href="https://github.com/LASER-Yi/homebridge-mi-acPartner#readme" target="_blank">Homebridge Mi Acpartner</a>

空调伴侣，可以通过高阶方法支持遥控更多红外设备。

<a rel="noreferrer noopener" href="https://github.com/alexgustafsson/homebridge-wol#readme" target="_blank">Homebridge WoL</a>

网络唤醒插件，通过它就能使用家庭APP启动支持网络唤醒的电脑或者服务器，还是通过SHH发送关机或者睡眠命令，让实现完美的开机关机效果。

<a rel="noreferrer noopener" href="https://github.com/pdiegmann/homebridge-synology-diskstation#readme" target="_blank">Homebridge Synology Diskstation</a>

唤醒或者关闭群晖NAS，以及查看系统温度。

<a href="https://github.com/Sunoo/homebridge-aqicn" target="_blank" rel="noreferrer noopener">homebridge-aqicn</a>

把本地的空气质量信息显示在 Homekit 上，五线小城市的数据也有。

上面就是我自己用到的 Homebridge 插件，附带的 Github 链接都有使用方法，有时间我会挑出几个插件来写下详细的教程。