---
layout: post
title: Lesson05-旋转动画
tags: osgjs官方教程笔记
categories: osgjs官方教程笔记
---
[官方效果展示](http://codepen.io/osgjs/pen/uxthp){:target="_blank"}

## 知识点

### 矩阵变换的回调 

[第二课]({{'/02-Animate-Light-Color/' |  prepend:site.url}}){:target="_blank"}讲过了光的回调，这里物体旋转功能实现使用的是矩阵变换的回调

核心代码如下：

```
var SimpleUpdateCallback = function () {};

SimpleUpdateCallback.prototype = {
    // rotation angle
    angle: 0,

    update: function ( node, nv ) {
        // rotation
        var m = node.getMatrix();
        osg.Matrix.makeRotate( -this.angle, 0.0, 0.0, 1.0, m );
        osg.Matrix.setTrans( m, 0, 0, 0 );
        this.angle += 0.1;
        return true;
    }
};

调用：
var cube = new osg.MatrixTransform();

// attache updatecallback function to cube
var cb = new SimpleUpdateCallback();
cube.addUpdateCallback( cb );
```

