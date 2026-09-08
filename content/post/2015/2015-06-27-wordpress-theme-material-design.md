---
title: WordPress 主题 Bliss 修改 Material Design 配色
author: 炒土豆丝
type: post
date: 2015-06-26T19:58:46+00:00
url: /wordpress-theme-material-design/
bluth_post_layout:
  - right_side
bluth_post_right_sidebar:
  - sidebar_right
bluth_post_left_sidebar:
  - sidebar_left
wpb_post_views_count:
  - 1872
duoshuo_thread_id:
  - 1278228446777966842
dsq_thread_id:
  - 3975480415
views:
  - 738
categories:
  - it
tags:
  - Material Design
  - WordPress

---
我现在使用的博客主题是 Bluthemes 开发的 Bliss 主题，极简卡片式的风格，用主题自带的蓝色主题。

## <a href="http://themeforest.net/item/bliss-personal-minimalist-wordpress-blog-theme/5423780" target="_blank">Bliss | Personal Minimalist WordPress Blog Theme</a>

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4248" src="https://wp-archive.baka.li/2015/06/old-Bliss-wordpress-theme.jpg" alt="old-Bliss-wordpress-theme" width="936" height="686" srcset="https://wp-archive.baka.li/2015/06/old-Bliss-wordpress-theme.jpg 936w, https://wp-archive.baka.li/2015/06/old-Bliss-wordpress-theme-150x110.jpg 150w, https://wp-archive.baka.li/2015/06/old-Bliss-wordpress-theme-300x220.jpg 300w" sizes="(max-width: 936px) 100vw, 936px" />][1]

最近，在物色  WordPress  主题的时候发现一个 Material Design 的主题的网站 <a href="http://MaterialWP.com" target="_blank">MaterialWP.com</a> ，很喜欢这网站首页配色。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4250" src="https://wp-archive.baka.li/2015/06/materialwp-com.png" alt="materialwp-com" width="1081" height="782" srcset="https://wp-archive.baka.li/2015/06/materialwp-com.png 1081w, https://wp-archive.baka.li/2015/06/materialwp-com-150x109.png 150w, https://wp-archive.baka.li/2015/06/materialwp-com-300x217.png 300w, https://wp-archive.baka.li/2015/06/materialwp-com-1024x741.png 1024w" sizes="(max-width: 1081px) 100vw, 1081px" />][2]

开始研究怎么把 Bliss 主题改成那种配色，首先得知道人家网站的颜色的 Hex 颜色代码，用 QQ 截图把光标移动到需要的颜色上能得到 RGB 颜色代码（ 48,63,159 ）。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4252" src="https://wp-archive.baka.li/2015/06/QQ-RGB-HEX.png" alt="QQ-RGB-HEX" width="579" height="334" srcset="https://wp-archive.baka.li/2015/06/QQ-RGB-HEX.png 579w, https://wp-archive.baka.li/2015/06/QQ-RGB-HEX-150x87.png 150w, https://wp-archive.baka.li/2015/06/QQ-RGB-HEX-300x173.png 300w" sizes="(max-width: 579px) 100vw, 579px" />][3]

用在线工具把 RGB 代码转换成为 Hex 代码（ #303F9F ）。

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4254" src="https://wp-archive.baka.li/2015/06/RGB-TO-HEX.png" alt="RGB-TO-HEX" width="884" height="423" srcset="https://wp-archive.baka.li/2015/06/RGB-TO-HEX.png 884w, https://wp-archive.baka.li/2015/06/RGB-TO-HEX-150x72.png 150w, https://wp-archive.baka.li/2015/06/RGB-TO-HEX-300x144.png 300w" sizes="(max-width: 884px) 100vw, 884px" />][4]

然后修改 Style.css ，技术太渣，怎么改都没用。

用最笨的方法，我找到了 Bliss 主题自定义 CSS 的文件，在主题目录下的 inc 目录的 custom-css.php ，在此文件的第 44 行开始。

<pre class="lang:php decode:true">case 'default';	
			$css_options['theme_color'] 							= '#45b0ee';
			$css_options['background_color'] 					= '#EDEDED';
			$css_options['top_banner_color'] 					= '#444444';
			$css_options['top_banner_font_color'] 		= '#FFFFFF';
			$css_options['top_banner_social_color']		= '#FFFFFF';
			$css_options['header_color'] 							= '#FFFFFF';
			$css_options['header_font_color'] 				= '#777777';
			$css_options['post_header_color'] 				= '#333333';
			$css_options['main_font_color'] 				= '#333333';
			$css_options['widget_header_color'] 			= '#FFFFFF';
			$css_options['widget_header_font_color'] 	= '#333333';
			$css_options['footer_color'] 							= '#333333';
			$css_options['footer_header_color'] 			= '#FFFFFF';
			$css_options['footer_font_color'] 				= '#FFFFFF';</pre>

需要修改的是 theme\_color （主题）、 background\_color （背景）、 top\_banner\_color （顶部）、header\_color （导航栏）和 footer\_color （低部）的颜色。

参照 <a href="http://MaterialWP.com" target="_blank">MaterialWP.com</a> 的颜色，我的改成了这样：

  * Top Banner：<span style="color: #3f51b5;">#3F51B5</span>
  * Background ：<span style="color: #e5e5e5;">#E5E5E5</span>
  * Header： <span style="color: #303f9f;">#303F9F</span>
  * Footer：<span style="color: #374147;">#374147</span>

<pre class="lang:php decode:true">case 'default';	
			$css_options['theme_color'] 							= '#4450C0';
			$css_options['background_color'] 					= '#E5E5E5';
			$css_options['top_banner_color'] 					= '#3F51B5';
			$css_options['top_banner_font_color'] 		= '#FFFFFF';
			$css_options['top_banner_social_color']		= '#FFFFFF';
			$css_options['header_color'] 							= '#303F9F';
			$css_options['header_font_color'] 				= '#FFFFFF';
			$css_options['post_header_color'] 				= '#212121';
			$css_options['main_font_color'] 				= '#333333';
			$css_options['widget_header_color'] 			= '#FFFFFF';
			$css_options['widget_header_font_color'] 	= '#333333';
			$css_options['footer_color'] 							= '#374147';
			$css_options['footer_header_color'] 			= '#374147';
			$css_options['footer_font_color'] 				= '#EEEEEE';</pre>

&nbsp;

改完颜色顺眼了很多，但是 Chrome 下字体都是宋体，在主题设置页自定义 CSS 里面添加这样一段就能把全部字体变成微软雅黑。

<pre class="lang:css decode:true">/* Primary Font Style */
                body, .font1, .font-primary, .commentlist, input{
                        font-family:Microsoft YaHei,Georgia, '冬青黑体简体中文 w3', Times, serif;
                }

        /* Header Font Style */
                h1, h2, h3, h4, h5, h6, .site-title{
                        font-family:Microsoft YaHei,Georgia, '冬青黑体简体中文 w3', Times, serif;
                }
</pre>

&nbsp;

装修好后特意上 OS X 上截个图，黑苹果的妙用&#8230;

[<img loading="lazy" decoding="async" class="alignnone size-full wp-image-4241" src="https://wp-archive.baka.li/2015/06/2015-Baka-House.png" alt="2015-Baka-House" width="1408" height="1059" srcset="https://wp-archive.baka.li/2015/06/2015-Baka-House.png 1408w, https://wp-archive.baka.li/2015/06/2015-Baka-House-150x113.png 150w, https://wp-archive.baka.li/2015/06/2015-Baka-House-300x226.png 300w, https://wp-archive.baka.li/2015/06/2015-Baka-House-1024x770.png 1024w" sizes="(max-width: 1408px) 100vw, 1408px" />][5]

 [1]: https://wp-archive.baka.li/2015/06/old-Bliss-wordpress-theme.jpg
 [2]: https://wp-archive.baka.li/2015/06/materialwp-com.png
 [3]: https://wp-archive.baka.li/2015/06/QQ-RGB-HEX.png
 [4]: https://wp-archive.baka.li/2015/06/RGB-TO-HEX.png
 [5]: https://wp-archive.baka.li/2015/06/2015-Baka-House.png