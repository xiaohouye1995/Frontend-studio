---
title: FrontendStudio 前端画室
date: 2020-05-15
categories:
- 项目实验室
tags: 
- hexo
- Valine
- fancybox
- 博客
---

个人博客网站，随缘记录一些或重要或无聊或精彩或平淡的事情。

{% note success %}
已开源
{% endnote %}

### DEMO

开源地址：https://github.com/xiaohouye1995/Frontend-studio
预览(国外)：https://xiaohouye1995.github.io  
预览(国内)：https://xiaohouye1995.gitee.io

## 框架/工具
- hexo https://hexo.io/zh-cn/
- hexo-theme-fluid https://github.com/fluid-dev/hexo-theme-fluid
- banner图片库 https://wallroom.io/
- Valine 评论插件 https://valine.js.org/quickstart.html
- fancybox 画廊插件 https://fancyapps.com/fancybox/3/docs/#setup
- 懒加载 lazyload https://github.com/tuupola/lazyload

## 功能需求
- [x] 研究室介绍演示、代码、demo、截图、文档
- [x] 文章、技术、随笔、诗词
- [x] 评论插件
- [x] 相册集
- [x] 暗黑模式
- [x] 游戏名作堂
- [ ] 诗词信笺模块

## 填坑

### TypeError $(...).lazyload is not a function
在$.getJSON() 方法下使用 Query.lazyload 懒加载插件时，会导致 $() 冲突。  
**解决方案：** 重新定义$()
```js
jQuery(document).ready(function ($) {
		$.getJSON("photos.json",function(result){
			// 相册数据
			let list =  result.photos
			console.log('list', list);
		    // 插入html
		    let dataHtml = '';
		    $('.photo-container').append(dataHtml);
			// 背景图懒加载
			$('div.lazy').lazyload();
		});
	})
```