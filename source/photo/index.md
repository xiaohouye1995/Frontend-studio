---
title: 时光画轴
date: 2020-02-23 19:20:33
banner_img_height: 0.001
---

<h1 class="title">且将新火试新茶，诗酒趁年华</h1>
<div class="card-container">
	<div class="card-wrap">
		<a href="https://frontend-studio-1256354221.file.myqcloud.com/photo/zhipai.jpg" data-fancybox="gallery"
		 data-caption="纸牌塔">
			<div class="card">
				<div class="card-bg" style="background-image: url(https://frontend-studio-1256354221.file.myqcloud.com/photo/zhipai.jpg);"></div>
				<div class="card-info">
					<h1 class="card-header">纸牌塔</h1>
					<p class="card-content">2020.5.13摄于杭州</p>
				</div>
			</div>
		</a>
	</div>
	<div class="card-wrap">
		<a href="https://frontend-studio-1256354221.file.myqcloud.com/photo/1991.jpg" data-fancybox="gallery" data-caption="1999">
			<div class="card">
				<div class="card-bg" style="background-image: url(https://frontend-studio-1256354221.file.myqcloud.com/photo/1991.jpg);"></div>
				<div class="card-info">
					<h1 class="card-header">1999</h1>
					<p class="card-content">十里湖光，对南屏晚妆。2019.11.16.摄于杭州西湖</p>
				</div>
			</div>
		</a>
	</div>
	<div class="card-wrap">
		<a href="https://unsplash.it/600.jpg?image=256" data-fancybox="gallery" data-caption="昆仑雪山">
			<div class="card">
				<div class="card-bg" style="background-image: url(https://unsplash.it/600.jpg?image=256);"></div>
				<div class="card-info">
					<h1 class="card-header">Canyons</h1>
					<p class="card-content">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
				</div>
			</div>
		</a>
	</div>
</div>
<script src="https://cdn.bootcdn.net/ajax/libs/jquery/3.5.1/jquery.js"></script>
<script src="https://cdn.staticfile.org/fancybox/3.5.7/jquery.fancybox.min.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdn.staticfile.org/fancybox/3.5.7/jquery.fancybox.min.css" />
<script>
	// fancyBox 灯箱插件
	$('[data-fancybox="gallery"]').fancybox({
		// Options will go here
	});
</script>
<style>
@media (min-width: 576px) {
	.container, .container-lg, .container-md, .container-sm, .container-xl {
	    max-width: 100%;
		padding-right: 0;
		padding-left: 0;
	}
	.row{
		margin-right: 0;
		margin-left: 0;
	}
}
#board {
	background-color: #3c4858;
}
.title {
	font-size: 26px;
	font-weight: 700f;
	color: #fff;
	text-align: center;
	margin-top: 8rem;
}
.card-container {
	margin: 40px 0;
	font-size: 14px;
	font-weight: 500;
	-webkit-font-smoothing: antialiased;
	display: flex;
	flex-wrap: wrap;
	justify-content: center;
}
.card-wrap {
	margin: 30px;
	transform: perspective(800px);
	transform-style: preserve-3d;
	cursor: pointer;
}
.card {
	position: relative;
	flex: 0 0 240px;
	width: 240px;
	height: 320px;
	background-color: #333;
	overflow: hidden;
	border: none;
	border-radius: 10px;
	box-shadow: 
		rgba(0,0,0, 0.66) 0 30px 60px 0,
		inset #333 0 0 0 5px,
		inset rgba(255,255,255, 0.5) 0 0 0 6px;
	transition: 1s cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
.card-bg {
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
.card-info {
	padding: 20px;
	position: absolute;
	bottom: 0;
	color: #fff;
	transform: translateY(40%);
	transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);
}
.card-info::after {
	content: '';
	position: absolute;
	top: 0;
	left: 0;
	z-index: 0;
	width: 100%;
	height: 100%;
	background-image: linear-gradient(to bottom, transparent 0%, rgba(0,0,0, 0.6) 100%);
	background-blend-mode: overlay;
	opacity: 0;
	transform: translateY(100%);
	transition: 2s 1s cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
.card-content {
	position: relative;
	z-index: 1;
	opacity: 0;
	text-shadow: rgba(0,0,0, 1) 0 2px 3px;
	transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);
	line-height: 1.5em;
}
.card-header {
	position: relative;
	z-index: 1;
	font-size: 24px;
	font-weight: 700;
	text-shadow: rgba(0,0,0, 0.5) 0 10px 10px;
}
.card-wrap:hover .card-info {
	transition: 0.6s cubic-bezier(0.23, 1, 0.32, 1);
	transform: translateY(0);
}
.card-wrap:hover .card-content {
	transition: 0.6s cubic-bezier(0.23, 1, 0.32, 1);
	opacity: 1;
}
.card-wrap:hover .card-info::after {
	transition: 2s cubic-bezier(0.23, 1, 0.32, 1);
	opacity: 1;
	transform: translateY(0);
}
.card-wrap:hover .card-bg {
	transition: 0.6s cubic-bezier(0.23, 1, 0.32, 1),
		opacity 2s cubic-bezier(0.23, 1, 0.32, 1);
	transform: translateX(10px) translateY(10px);
	opacity: 0.8;
}
.card-wrap:hover .card {
	transition:
		0.6s cubic-bezier(0.23, 1, 0.32, 1),
		box-shadow 2s cubic-bezier(0.23, 1, 0.32, 1);
	box-shadow:
		rgba(255,255,255, 0.2) 0 0 40px 5px,
		rgba(255,255,255, 1) 0 0 0 1px,
		rgba(0,0,0, 0.66) 0 30px 60px 0,
		inset #333 0 0 0 5px,
		inset #fff 0 0 0 6px;
}
</style>