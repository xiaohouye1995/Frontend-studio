---
title: 疯狂贪吃龙 CrazyDragon
date: 2021-03-30
categories:
- 项目实验室
tags: 
- Cocos Creator
---

## DEMO

![预览1](https://sns-img-hw.xhscdn.com/d2097e64-cc36-c791-7c53-37d68ad7ad10?imageView2/2/h/1200/format/webp)

## 微信小程序码

![小程序码](https://navigation-1256354221.cos.ap-shanghai.myqcloud.com/icons/QR_flappyDragon.jpeg)

## 运行平台

微信小游戏

## 框架/工具

[Cocos Creator](https://www.cocos.com/products#CocosCreator)  
[opengameart 游戏素材](https://opengameart.org/)  
[爱给网 音效](https://www.aigei.com/s?q=&type=sound)

## 文档

[flappy bird](https://blog.csdn.net/u012987441/category_9330235.html)  
[flappy text](https://codepen.io/sakri/pen/eukbC)

## 功能需求

- [x] 追随者动态跟随
- [x] 追随者果实，获取后增加追随者
- [ ] 保护盾果实，获取后免碰撞一次
- [ ] 冲刺果实，获取后加速5秒，期间无敌
- [ ] 好友排行榜
- [ ] 适配ipad
- [ ] 美化分数显示，可以改为飞行里数
- [ ] 水平视差滚动

## 填坑

### 项目导入后，层级管理器无数据

点击 Scene 中的 main 文件，初始化项目

### 动态跟随逻辑

```js
// 身体飞行轨迹
for(var i = 0; i < this.mainControl.body.length; i++){
	if (i === 0) {
		this.mainControl.body[i].y = this.node.y - (this.node.y - this.mainControl.body[i].y) * .9;
	} else {
		this.mainControl.body[i].y = this.mainControl.body[i-1].y - (this.mainControl.body[i-1].y - this.mainControl.body[i].y) * .9;
	}
}
```