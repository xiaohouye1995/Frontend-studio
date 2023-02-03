---
title: 休对故人思故国，且将新火试新茶。诗酒趁年华。
date: 2020-02-23 19:20:33
banner_img: https://frontend-studio-1256354221.file.myqcloud.com/photo/photo_banner.jpeg
banner_img_height: 100
---

<div class="photo-container">
</div>
<script src="https://cdn.staticfile.org/jquery/3.4.1/jquery.js"></script>
<script src="https://cdn.staticfile.org/fancybox/3.5.7/jquery.fancybox.min.js"></script>
<script src="https://cdn.staticfile.org/jquery.lazyload/1.9.1/jquery.lazyload.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdn.staticfile.org/fancybox/3.5.7/jquery.fancybox.min.css" />
<script>
	jQuery(document).ready(function ($) {
		$.getJSON("photos.json",function(result){
			// 相册数据
			let list =  result.photos
		    // 插入html
		    let dataHtml = '';
		    for (let item of list) {
		    	dataHtml += `<div class="photo-wrap"><figure>`;
		    	dataHtml += `<a href="${item.imgSrc}" data-fancybox="gallery" data-width="800">`;
		    	dataHtml += `<div class="photo">`;
		    	dataHtml += `<div class="photo-bg lazy" style="background-image: url('/img/loading.gif')" data-original="${item.imgSrc}"></div>`
		    	dataHtml += `<div class="photo-info">`;
		    	dataHtml += `<h1 class="photo-header">${item.title}</h1>`;
		    	dataHtml += `<p class="photo-content">${item.info}</p>`;
		    	dataHtml += `</div>`;
		    	dataHtml += `</div>`;
		    	dataHtml += `<figcaption>`;
		    	dataHtml += `<h5>${item.title}</h5>`;
		    	dataHtml += `<p>${item.info}</p>`;
		    	dataHtml += `</figcaption>`;
		    	dataHtml += `</a>`;
		    	dataHtml += `</figure></div>`;
		    }
		    $('.photo-container').append(dataHtml);
			// 背景图懒加载
			$('div.lazy').lazyload();
			// fancyBox 灯箱插件
			$('[data-fancybox="gallery"]').fancybox({
				// 设置相册介绍
				caption: function(instance, item) {
					return $(this).find('figcaption').html();
				}
			});
		});
	})
</script>
<style>
main .container{
	max-width: 100%;
	padding-right: 0;
	padding-left: 0;
}
main .container .row {
	margin: 0;
}
#board {
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
}
figcaption {
  display: none;
}
.title {
	font-size: 26px;
	font-weight: 700f;
	color: #fff;
	text-align: center;
	margin-top: 8rem;
}
.photo-container {
	font-size: 14px;
	font-weight: 500;
	-webkit-font-smoothing: antialiased;
	display: flex;
	flex-wrap: wrap;
	justify-content: center;
}
.photo-wrap {
	margin: 30px;
	transform: perspective(800px);
	transform-style: preserve-3d;
	cursor: pointer;
	border-radius: 10px;
}
.photo {
	position: relative;
	flex: 0 0 240px;
	width: 240px;
	height: 320px;
	background-color: #333;
	overflow: hidden;
	border: none;
	border-radius: 10px;
	box-shadow:
		rgba(0, 0, 0, 0.66) 0 30px 60px 0,
		inset #333 0 0 0 5px,
		inset rgba(255, 255, 255, 0.5) 0 0 0 6px;
	transition: 1s cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
.photo-bg {
	opacity: 0.5;
	position: absolute;
	top: -20px;
	left: -20px;
	width: 100%;
	height: 100%;
	padding: 20px;
	box-sizing: content-box;
	background-repeat: no-repeat;
	background-position: center;
	background-size: cover;
	transition:
		1s cubic-bezier(0.445, 0.05, 0.55, 0.95),
		opacity 2s 1s cubic-bezier(0.445, 0.05, 0.55, 0.95);
	pointer-events: none;
}
.photo-info {
	padding: 20px;
	position: absolute;
	bottom: 0;
	color: #fff;
	transform: translateY(40%);
	transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);
}
.photo-info::after {
	content: '';
	position: absolute;
	top: 0;
	left: 0;
	z-index: 0;
	width: 100%;
	height: 100%;
	background-image: linear-gradient(to bottom, transparent 0%, rgba(0, 0, 0, 0.6) 100%);
	background-blend-mode: overlay;
	opacity: 0;
	transform: translateY(100%);
	transition: 2s 1s cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
.photo-content {
	position: relative;
	z-index: 1;
	opacity: 0;
	text-shadow: rgba(0, 0, 0, 1) 0 2px 3px;
	transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);
	line-height: 1.5em;
}
.photo-header {
	position: relative;
	z-index: 1;
	font-size: 36px;
	font-weight: 700;
	text-shadow: rgba(0, 0, 0, 0.5) 0 10px 10px;
}
.photo-wrap:hover .photo-info {
	transition: 0.6s cubic-bezier(0.23, 1, 0.32, 1);
	transform: translateY(0);
}
.photo-wrap:hover .photo-content {
	transition: 0.6s cubic-bezier(0.23, 1, 0.32, 1);
	opacity: 1;
}
.photo-wrap:hover .photo-info::after {
	transition: 2s cubic-bezier(0.23, 1, 0.32, 1);
	opacity: 1;
	transform: translateY(0);
}
.photo-wrap:hover .photo-bg {
	transition: 0.6s cubic-bezier(0.23, 1, 0.32, 1),
		opacity 2s cubic-bezier(0.23, 1, 0.32, 1);
	transform: translateX(10px) translateY(10px);
	opacity: 0.8;
}
.photo-wrap:hover .photo {
	transition:
		0.6s cubic-bezier(0.23, 1, 0.32, 1),
		box-shadow 2s cubic-bezier(0.23, 1, 0.32, 1);
	box-shadow:
		rgba(255, 255, 255, 0.2) 0 0 40px 5px,
		rgba(255, 255, 255, 1) 0 0 0 1px,
		rgba(0, 0, 0, 0.66) 0 30px 60px 0,
		inset #333 0 0 0 5px,
		inset #fff 0 0 0 6px;
}
</style>