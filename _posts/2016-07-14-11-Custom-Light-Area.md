---
layout: post
title: Lesson11-自定义光照范围
tags: osgjs官方教程笔记
categories: osgjs官方教程笔记
---
[官方效果展示](http://codepen.io/osgjs/pen/KIlrg)



## 知识点

### 着色器代码写在.html文件中
```
<script id="vertex-vs" type="x-shader/x-vertex">
    ...
</script>

<script id="fragment-fs" type="x-shader/x-fragment">
    ...
</script>
```


### 创建球体

```
var targetModel2 = osg.createTexturedSphere( 10, 30, 30 );

//var createTexturedSphere = function ( radius, widthSegments, heightSegments, phiStart, phiLength, thetaStart, thetaLength ) {}
```

### 单面渲染

```
lightNode.getOrCreateStateSet().setAttributeAndModes( new osg.CullFace( 'BACK' ) );
```
[第一课]()里面提到过 CullFace，这里复习一下;
osgjs里面CullFace的枚举值为：
- CullFace.DISABLE = 0x0;
- CullFace.FRONT = 0x0404;
- CullFace.BACK = 0x0405;
- CullFace.FRONT_AND_BACK = 0x0408;