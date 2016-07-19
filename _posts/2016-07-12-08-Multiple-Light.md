---
layout: post
title: Lesson08-多光源
tags: osgjs官方教程笔记
categories: osgjs官方教程笔记
---
[官方效果展示](http://codepen.io/osgjs/pen/pEvmo)

 看一下整个程序的节点结构：
 
![Alt text](http://oa1dh8fyl.bkt.clouddn.com/osg-Lesson08.svg)


## 知识点

### 灯光属性设置
灯光的概念、使用和 [webgl的灯光](http://www.glprogramming.com/red/chapter05.html) 一致

这里对于光照大部分参数进行了设置

```
var lightnew = new osg.Light( i );

// pretty spotlight fallof showing
// clearly directions
lightnew.setSpotCutoff( 254 );				//照射范围
lightnew.setSpotBlend( 1.0 );				//		
lightnew.setConstantAttenuation( 0 );		//衰减常数
lightnew.setLinearAttenuation( 0.005 );		//线性衰减
lightnew.setQuadraticAttenuation( 0 );		//二次衰减
lightnew.setName( 'light' + i );
lightnew._enabled = true;

// red light
mainNode.lights[ 0 ].setAmbient( [ 0.0, 0, 0.0, 1.0 ] );//环境光
mainNode.lights[ 0 ].setDiffuse( [ 1.0, 0, 0.0, 1.0 ] );//漫反射
mainNode.lights[ 0 ].setSpecular( [ 1.0, 0, 0.0, 1.0 ] );//镜面反射
```

### osg.Vec3的运算
js中用到了  sub 和 dot 运算，这些运算在 sources/osg/vec3.js 里面，比较容易理解，直接看源码就明白了

```
dot: function ( a, b ) {
    return a[ 0 ] * b[ 0 ] + a[ 1 ] * b[ 1 ] + a[ 2 ] * b[ 2 ];
},

sub: function ( a, b, r ) {
    r[ 0 ] = a[ 0 ] - b[ 0 ];
    r[ 1 ] = a[ 1 ] - b[ 1 ];
    r[ 2 ] = a[ 2 ] - b[ 2 ];
    return r;
},
```
