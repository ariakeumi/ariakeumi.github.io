---
title: "一键安装配置 Anytls 和 Snell v5 协议"
description: ""
date: 2026-06-15
draft: false
image: gfw.png
categories: ["it"]
tags: ["科学上网"]
url: /anytls-snell-vpn
---

## 记录

今年的 64 大考没过 ，有两台 VPS 的 IP 被封。

6 月 3 号下午 4 点，DMIT IP 被封，当天同一时段有大量 DMIT 和 BWG 的 IP 被封禁，导致能免费更换 IP 的 DMIT 已经没有 IP 给用户换了，IP 在七天后解封。

6 月 9 号下午 1点，xTom IP 被封，都过了几天了依旧被封让我很震惊，五天后解封。

## 协议对比

两台 VPS 上都通过 3x-ui 部署了 Trojan 和 Vless (xtls-rprx-vision) 协议，过去几年都顺过度过 64 ，最严重的情况也就是 Trojan 所用的端口被封禁。

今年的情况前所未有，明年肯定是不能再用这三板斧了。

了解了下最新的流行的协议，让 ChatGPT 总结了优缺点：

| 协议           | 优点                                                         | 缺点                                                         |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Hysteria 2** | • 基于 QUIC/UDP，速度快• 抗丢包能力强• 高延迟线路表现优秀• 支持 UDP（游戏、语音） | • 依赖 UDP 质量• 部分网络会限速 UDP• 流量特征较明显          |
| **AnyTLS**     | • 流量最接近正常 HTTPS• 隐蔽性较好• 配置简单• TCP 网络稳定   | • 丢包环境性能一般• 客户端生态较小                           |
| **Snell v5**   | • 部署极其简单• 性能优秀• 延迟低、资源占用小• Surge 生态支持好 | • 闭源协议• 官方实现独家维护• 客户端选择较少• 伪装能力不如 AnyTLS |

首先排除 Hysteria 2 ，我的机器都是优化线路，不需要 UDP 暴力发包，隐匿性更重要。

Snell 是 Surge 作者开发的，风评有点差，PASS 掉，最终选择了 AnyTLS 。

## AnyTLS 配置

我选择自己最喜欢的 Docker 方式安装，一行命令完整部署，最方便。

首先安装 Docker :

```
curl -sSL https://get.docker.com/ | sh
systemctl start docker
systemctl enable docker
```

安装 AnyTLS 服务端

只需要把 密码 (MIMA) 和 端口 (PORT) 替换成自己的就可以了。

```
docker run -d \
  --name anytls \
  --restart always \
  --network host \
  -e TZ=Asia/Shanghai \
  -e MIMA=dWV02S8KQzVMmr \
  -e PORT=5443 \
  jonnyan404/anytls
```

客户端我用的 OpenClash (mihomo 内核) ，配置也很简单，填 IP 端口密码就行，也不再需要证书和域名什么的。

```
  - name: Anytls
    type: anytls
    server: IP地址
    port: 端口
    password: "密码"
    client-fingerprint: chrome
    udp: true
    skip-cert-verify: true
```

## Snell v5 配置

用了几天 AnyTLS ，没什么大问题，就是延迟测试的时候相比其他协议不太稳定，忽高忽低。

据说现在机场很爱用 AnyTLS ，感觉以后会被重点关照。

决定再部署个  Snell  ，客户端方面 mihomo 都支持 Snell v5 ，不一定要用 Surge 。

Snell v6 已经出了，等客户端跟上再升级。

同样通过 Docker 安装，替换端口和 PSK (8-16 位随机数)就行。

```
docker run -d --name snell \
  --restart unless-stopped \
  --network host \
  -e SNELL_PORT=5443 \
  -e SNELL_PSK=xxxx826535a6197fdbe28715e88cxxxx \
  -e SNELL_VER=v5 \
  jinqians/snell-server:latest
```

客户端配置：

```
  - name: Snell
    type: snell
    server: IP 地址
    port: 端口
    psk: 密钥
    version: 5
    udp: true
```

