---
title: WebKit, WebKit2,Blink Chromium和Chrome介绍
date: 2016-08-26 15:45:06
categories:
- WebKit
tags: WebKit
---
>原文地址：http://blog.csdn.net/milado_nju/article/details/7216067

>备注：对原文做了一定程度删减。

### WebKit
前身是KDE的KHTML和KJS，是一个渲染引擎，不是一个浏览器，也不想成为浏览器
第一是WebCore，其中包含了对HTML，CSS等很多W3C规范的实现；第二部分就是狭义上的WebKit，它主要是各个平台的的移植并提供相对应的Web接口，也就是WebView或者类似WebView，这些接口提供操作和显示网页的能力。

### WebKit2
它不是WebKit简单的第二个版本，它是一个新的API层，其最主要的变化在于将网页的渲染置于单独的进程，而接口层则在另外一个进程，它们之间通过IPC来通讯。对于接口的调用者来说，中间的IPC和底下的实现是透明的，这样做的好处有很多，一个很明显的好处是，当网页的渲染出现问题时，不会阻碍Web接口的调用者进程，这会在很大程度上解决或者帮助解决浏览器或者这些调用者的稳定性和安全性等问题

### Blink
Google因为开发思想和原来的Webkit2开发社区产生了冲突，所以就脱离了Webkit项目，成立了Blink项目，但是不是一个全新的引擎，目前就是从WebKit直接复制出一个版本出来，然后将与chromium无关的Ports全部移除掉，将代码结构重新整理,不是一个全新的渲染引擎

### Chromium
一个建立在WebKit之上的浏览器**开源项目**，由Google发起的。该项目被创建以来发展迅速，很多先进的技术被采用，如跨进程模型，沙箱模型等等。同时，很多新的规范被支持，例如WebGL，Canvas2D，CSS3以及其他很多的HTML5特性，基本上每天你都可以看到它的变化，它的版本升级很快。在性能方面，其也备受称赞，包括快速启动，网页加载迅速等。

### Chrome
Google公司的浏览器产品,它基于chromium开源项目，一般选择稳定的版本作为它的基础，它和chromium的不同点在于chromium是开源试验场，会尝试很多新的东西，当这些东西稳定之后，chrome才会集成进来，这也就是说chrome的版本会落后于chromium。
chrome还会整合Google的很多服务， 最后chrome还会有自动更新的功能，这也是chromium所没有的。