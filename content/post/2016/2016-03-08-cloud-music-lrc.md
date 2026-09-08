---
title: 下载网易云音乐的双语歌词
author: 炒土豆丝
type: post
date: 2016-03-08T06:25:12+00:00
url: /cloud-music-lrc/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 5744
dsq_thread_id:
  - 4643715782
views:
  - 867
argon_hide_readingtime:
  - 'false'
argon_meta_simple:
  - 'false'
argon_first_image_as_thumbnail:
  - default
argon_show_post_outdated_info:
  - default
categories:
  - music

---
 

网易云音乐是国内最好的音乐平台，歌曲丰富，而且很多外语歌都有双语歌词。但是网易云音乐不提供歌词下载，用手机客户端可以一键获取，但是获取到的歌词并非 LRC 格式的，而且文件名是纯数字，不方便用。

在 PC 端，可以通过一段 JS 脚本直接获取到双语的歌词。

## 使用方法： 

  * 打开需要下载歌词的歌曲网易云音乐链接，通过地址栏&nbsp;URL 获取到歌曲 ID 。

[<img loading="lazy" decoding="async" width="517" height="135" src="https://wp-archive.baka.li/2016/03/cloud-music-lrc-1.png" alt="cloud-music-lrc-1" class="wp-image-4792" srcset="https://wp-archive.baka.li/2016/03/cloud-music-lrc-1.png 517w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-1-150x39.png 150w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-1-300x78.png 300w" sizes="(max-width: 517px) 100vw, 517px" />][1] 

  * 按 F12 打开审查元素（Chrome浏览器），点击 Console 。

[<img loading="lazy" decoding="async" width="826" height="492" src="https://wp-archive.baka.li/2016/03/cloud-music-lrc-3.png" alt="cloud-music-lrc-3" class="wp-image-4793" srcset="https://wp-archive.baka.li/2016/03/cloud-music-lrc-3.png 826w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-3-150x89.png 150w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-3-300x179.png 300w" sizes="(max-width: 826px) 100vw, 826px" />][2] 

  * 把下面代码最后一行里面的歌曲 ID 替换成自己需要下载歌词的歌曲 ID ，复制粘贴并回车运行。

<pre class="wp-block-code"><code>(function(songID){
    var xhr = new XMLHttpRequest();
    xhr.open('GET', 'http://music.163.com/api/song/lyric?lv=-1&tv=-1&id=' + songID, true);
    xhr.send();
    xhr.onload = function() {
        var data = JSON.parse(xhr.responseText);
        var lrc = data.lrc.lyric.match(/\&#91;\d+:\d+\.\d+&#91;^\&#91;]+/g);
        var tLrc = data.tlyric.lyric.match(/\&#91;\d+:\d+\.\d+&#91;^\&#91;]+/g);
        var newLrc = &#91;];
        lrc.map(function() {
            newLrc.push(lrc&#91;arguments&#91;1]]);
            newLrc.push(tLrc&#91;arguments&#91;1]]);
        });
        window.open('', "_blank", '').document.write(newLrc.join('&lt;br>'));
    };
}('28870317')); // 歌曲 ID</code></pre>

  * 弹出阻止运行窗口请允许。

[<img loading="lazy" decoding="async" width="610" height="416" src="https://wp-archive.baka.li/2016/03/cloud-music-lrc-2.png" alt="cloud-music-lrc-2" class="wp-image-4794" srcset="https://wp-archive.baka.li/2016/03/cloud-music-lrc-2.png 610w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-2-150x102.png 150w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-2-300x205.png 300w" sizes="(max-width: 610px) 100vw, 610px" />][3] 

  * 完美得到带时间轴的双语歌词，自行保存为 LRC 格式就好了，或者直接嵌入歌曲标签里面。

[<img loading="lazy" decoding="async" width="624" height="487" src="https://wp-archive.baka.li/2016/03/cloud-music-lrc-4.png" alt="cloud-music-lrc-4" class="wp-image-4795" srcset="https://wp-archive.baka.li/2016/03/cloud-music-lrc-4.png 624w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-4-150x117.png 150w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-4-300x234.png 300w, https://wp-archive.baka.li/2016/03/cloud-music-lrc-4-194x150.png 194w" sizes="(max-width: 624px) 100vw, 624px" />][4] 

感谢 V2EX 用户 <a href="https://www.v2ex.com/member/demo" target="_blank" rel="noopener">demo</a>&nbsp;贡献此脚本。

GitHub地址：<span class="author"><span class="url fn">anonymous</span></span><span class="path-divider">/</span><strong class="gist-header-title css-truncate-target"><a href="https://gist.github.com/anonymous/a800677393bbb2dd113a">concat_163_music_lrc.js</a></strong>

 [1]: https://wp-archive.baka.li/2016/03/cloud-music-lrc-1.png
 [2]: https://wp-archive.baka.li/2016/03/cloud-music-lrc-3.png
 [3]: https://wp-archive.baka.li/2016/03/cloud-music-lrc-2.png
 [4]: https://wp-archive.baka.li/2016/03/cloud-music-lrc-4.png