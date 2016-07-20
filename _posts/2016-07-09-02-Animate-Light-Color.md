---
layout: post
title: Lesson02-光的动画效果
tags: osgjs官方教程笔记
categories: osgjs官方教程笔记
---

[官方效果展示](http://codepen.io/osgjs/pen/xzeFH){:target="_blank"}

看到源码是不是很开心，很熟悉^^

新面孔只有灯光部分

## 知识点

###  灯光
```
// we create a Callback   回调函数，只有灯光一直在变
var LightUpdateCallback = function () {};
LightUpdateCallback.prototype = {
	update: function ( node, nv ) {
		//every 5 seconds
		var currentTime = nv.getFrameStamp().getSimulationTime();
		currentTime = ( ( currentTime % 5 ) / 5 );
		// light goes from black to red
		//设置漫反射颜色，currentTime 的值为红色分量的值 
		node.getLight().setDiffuse( [ currentTime, 0.0, 0.0, 0.0 ] );
		node.traverse( nv );
	}
};
// the light itself
var lightSource = new osg.LightSource();
var lightNew = new osg.Light();
lightSource.setUpdateCallback( new LightUpdateCallback() );
lightSource.setLight( lightNew );

```
可以看到光源(LightSource)对象(可以看成是灯光的容器)，包含一个设置回调函数的方法，而且回调函数必须实现 update 方法，该方法中可以拿到的参数分别为LightSource对象和UpdateVisitor 对象

注意：可以设置多个回调函数
getUpdateCallback 只能获取到第一个回调函数
getUpdateCallbackList 可以获取所有的回调函数
