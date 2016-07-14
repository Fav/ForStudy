---
layout: post
title: Lesson04-自定义着色器
tags: osgjs
categories: osgjs官方教程笔记
---

[官方效果展示](http://codepen.io/osgjs/pen/hzfvq)

着色器的使用请参考《WebGL编程指南》第二章入门的“着色器是什么”

## 知识点

### 材质
```
var material = new osg.Material();
material.setDiffuse( [ 1, 0, 0, 1 ] );
material.setAmbient( [ 1, 0, 0, 1 ] );
```
>状态属性类 osg::Material 封装了 OpenGL 的 glMaterial()和 glColorMaterial()指令的函数功能。要在用户应用程序中设置材质属性，首先要创建一个Material对象，设置颜色和其它参数，然后关联到场景图形的StateSet 中。

>Material 类允许用户设置全局、散射、镜面反射和放射材质的颜色，以及镜面和高光指数参数。 Material 类定义了枚举量 FRONT ， BACK 和FRONT_AND_BACK，以便用户程序为几何体的正面和背面的设置材质属性。举例来说，下面的代码为一个几何图元的正面设置了散射颜色，镜面反射颜色和镜面指数的参数。 
 
### 动态参数
```
//automatic UI shader binding
var parameterVisitor = new osgUtil.ParameterVisitor();
parameterVisitor.setTargetHTML( document.getElementById( 'Parameters' ) );
target.accept( parameterVisitor );

 { \"min\": 0.0,  \"max\": 0.8, \"step\": 0.01, \"value\": 0.2 } ',
```
osgUtil.ParameterVisitor 提供了关联DOM元素与参数的桥梁；

这里setTargetHTML 之后就在 div#Parameters创建了density这个滑动条，而执行accept操作之后设定了滑动条的范围，最大值0.81 是根据max 和 step计算来；其中值的传递是通过HTML5 LocalStorage 本地存储技术进行的。

### 视图
```
viewer = new osgViewer.Viewer( canvas, {
    antialias: true,
    alpha: true
} );
```
可以设置的参数有以下一些"

+ alpha: true

+ antialias: true

+ enableFrustumCulling: false

+ fullscreen: true

+ scrollwheel: true

+ stats: false

+ webgl2: false


