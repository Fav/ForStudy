---
layout: post
title: Lesson12-阴影基础
tags: osgjs官方教程笔记
categories: osgjs官方教程笔记
---
[官方效果展示](http://codepen.io/osgjs/pen/qEmxov){:target="_blank"}


## 知识点

### 阴影

```
/////////////////// Shadow
var shadowedScene = new osgShadow.ShadowedScene();
shadowedScene.addChild( scene );

var shadowSettings = new osgShadow.ShadowSettings();

shadowSettings.setLight( lightNew );

var shadowMap = new osgShadow.ShadowMap( shadowSettings );
shadowedScene.addShadowTechnique( shadowMap );
shadowMap.setShadowSettings( shadowSettings );

mainNode.addChild( shadowedScene );
/////////////////// Shadow end
```
可以看到阴影的实现是在 osgShadow，而光照是在osg 模块下；
整个代码结构如下：

![物体结构]({{"/osg-Lesson12.jpg" | prepend: site.imgblog }})

