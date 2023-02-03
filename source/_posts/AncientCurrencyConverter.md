---
title: AncientCurrencyConverter 古代银钱换算器
date: 2020-03-30
categories:
- 项目实验室
tags: 
- uni-app
- vue
---

古代的一两(文、贯、钱)等于现在的多少钱？当你有这个疑惑时，可以使用古代银钱换算器来进行换算。

**算法公式：** 底层工人、百姓勉强维持温饱的月入（银两、文钱、布帛、银元）=现如今底层工人、百姓勉强维持温饱的月入（人民币）

**示例：**  
清乾隆二年(1737年)浙江泰顺，月工工价为0.6两白银。来源：中国第一历史档案馆乾隆刑科题本，命案档，档号0045。  
中国2019年北京市最低工资为2200元。来源：北京市人力资源和社会保障局。因此可知1737年的0.6两约等于 2019年的2200元，换算得出：  
**1两（白银） = 3666.67元（人民币）

## DEMO

![预览1](https://sns-img-hw.xhscdn.com/862b008a-7dd2-4a20-c4be-dbbdf39c2ff5?imageView2/2/h/1200/format/webp)

## 微信小程序码

![小程序码](https://navigation-1256354221.cos.ap-shanghai.myqcloud.com/icons/QR_AncientCurrencyConverter.jpeg)

## 运行平台

微信小程序、支付宝小程序、H5、ios、安卓

使用 uni-app 开发，除微信小程序外，其他端未测试

## 框架/工具

- uni-app
- 算法规则依据 https://zhuanlan.zhihu.com/p/32089267
- 小程序富文本插件Parser https://github.com/jin-yufeng/Parser
- iconfont [https://www.iconfont.cn/](https://www.iconfont.cn/)
- UEditor 富文本编辑器 http://ueditor.baidu.com/website/onlinedemo.html
- 腾讯云存储
- 图片压缩picdiet https://www.picdiet.com/zh-cn

## 功能需求

- [x] 意见反馈
- [ ] 彩蛋 （等待你的发现~~）
- [x] 转发分享
- [ ] 适配小程序pc（ipad）端
- [ ] 支付宝版小程序
- [ ] H5版
- [x] 各朝代货币图片及介绍，折叠面板，图片点击放大
- [ ] 国外货币换算
- [ ] 补全各朝代工价
- [x] 多列选择器，朝代-时期
- [ ] 暗黑模式
- [ ] 更多-货币换算列表
- [ ] 转uniCloud
- [ ] 年号换算公元历

## 技巧

### css绝对定位(absolute)居中方法

```
.panel {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
}
```

### 小程序图片缓存策略

服务器图片更新后，小程序本地因为缓存，导致图片没有更改。  
[https://www.jianshu.com/p/65710ab69c3b](https://www.jianshu.com/p/65710ab69c3b)

