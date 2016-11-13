---
layout: post
title: cesium-Animation
tags: cesiumjs
categories: cesiumjs文档
---

调用方法new Cesium.Animation(container, viewModel)

Name	|Type	|Description
---|---|---
container	|Element or String	| DOM节点对象或者ID
viewModel	|[AnimationViewModel]()	| 视图模式

提供了播放，暂停，回放，当前时间，日期和速度调节环，类似影音播放器的操作方式

Animation 部件在左上角提供了同步时间的按钮。如果当前时间在时钟的起始和终止之间段外，这个模式在 ClockRange.CLAMPED 或者 ClockRange.LOOP_STOP 模式下无效。

~~~javascript
// In HTML head, include a link to Animation.css stylesheet,
// and in the body, include: <div id="animationContainer"></div>

var clock = new Cesium.Clock();
var clockViewModel = new Cesium.ClockViewModel(clock);
var viewModel = new Cesium.AnimationViewModel(clockViewModel);
var widget = new Cesium.Animation('animationContainer', viewModel);

function tick() {
    clock.tick();
    Cesium.requestAnimationFrame(tick);
}
Cesium.requestAnimationFrame(tick);
~~~

### 属性
***
+ **readonly** container : Element  
+ **readonly** viewModel : AnimationViewModel  

### 方法
***
+ applyThemeChanges()
根据css设置部件主题样式是，调用此方法让主题生效

~~~
document.body.className = 'cesium-lighter';
viewer.animation.applyThemeChanges();
~~~

+ destroy()
+ isDestroyed() → Boolean
+ resize()