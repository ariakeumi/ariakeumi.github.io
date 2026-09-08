---
title: Linux 下限制某进程的 CPU 使用率
author: 炒土豆丝
type: post
date: 2015-12-10T05:44:21+00:00
url: /linux-cpulimit/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 2950
dsq_thread_id:
  - 4391087488
views:
  - 760
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - it
tags:
  - Linux

---
最近游戏服务器出了点小问题，某个日志文件以每秒数 MB 的速度增大，最后达到 28GB 吃满了磁盘&#8230;

[<img loading="lazy" decoding="async" width="551" height="237" src="https://wp-archive.baka.li/2015/12/secagent-log.png" alt="secagent-log" class="wp-image-4751" srcset="https://wp-archive.baka.li/2015/12/secagent-log.png 551w, https://wp-archive.baka.li/2015/12/secagent-log-150x65.png 150w, https://wp-archive.baka.li/2015/12/secagent-log-300x129.png 300w" sizes="(max-width: 551px) 100vw, 551px" />][1] 

这个叫 Secagent 的进程都不知道是干嘛的，日志都是重复这两句错误。

貌似是很专业的东西，能搜到的资料太少，删掉 log 文件夹就好了&#8230;

<pre class="wp-block-code"><code>&#91;zenlib] 1 Pipe is full or data small?,Some data can't put to pipe. Please increase and check. nodesize=120, freesize=38
&#91;ERROR]&#91;virtual int SecAgentApp::proc(size_t&)], proc sdk msg error, ret = 5014</code></pre>

然后更严重的问题是，Secagent 这个进程会发疯般的占用 CPU 。

无法从根源上解决问题，只好用最愚蠢的办法了，直接限制这个进程的 CPU 使用率。

在 CentOS 上安装 Cpulimit ：

<pre class="wp-block-code"><code>wget -O cpulimit.zip https://github.com/opsengine/cpulimit/archive/master.zip
unzip cpulimit.zip
cd cpulimit-master
make
sudo cp src/cpulimit /usr/bin</code></pre>

ps 我的 Linux 端连 wget 和 zip 都被精简掉了，只好解压好才传过去。

安装好 Cpulimit 后，使用 top 命令查看进程的 PID ，然后就可以用它来限制进程的 CPU 使用率了：

<pre class="wp-block-code"><code>cpulimit -l 0.1 -p 1346    #0.1指CPU使用率限制为0.1%，1346是进程PID</code></pre>

[<img loading="lazy" decoding="async" width="719" height="400" src="https://wp-archive.baka.li/2015/12/linux-cpulimit.png" alt="linux-cpulimit" class="wp-image-4750" srcset="https://wp-archive.baka.li/2015/12/linux-cpulimit.png 719w, https://wp-archive.baka.li/2015/12/linux-cpulimit-150x83.png 150w, https://wp-archive.baka.li/2015/12/linux-cpulimit-300x167.png 300w" sizes="(max-width: 719px) 100vw, 719px" />][2] 

限制了 CPU 使用率后日志的问题也随之解决了。

[1]: https://wp-archive.baka.li/2015/12/secagent-log.png
[2]: https://wp-archive.baka.li/2015/12/linux-cpulimit.png