---
layout: post
title: Lesson06-高级定制着色器
tags: osgjs官方教程笔记
categories: osgjs官方教程笔记
---
[官方效果展示](http://codepen.io/osgjs/pen/Ffhrc){:target="_blank"}

着色器的使用请参考《WebGL编程指南》第二章入门的“着色器是什么”以及第六章“OpenGL ES 着色器语言(GLSL ES)”

## 知识点

### 着色器传值
 
```
//color = osg.Uniform.createVec4(vec4(1,1,0,0),'color');
var lightPos = osg.Uniform.createFloat3( [ 0, 0, -10 ], 'lightPos' );
target.getOrCreateStateSet().addUniform( lightPos );
target2.getOrCreateStateSet().addUniform( lightPos );

'uniform vec4 lightPos;',
```

### 形状变化
形状改变是在顶点着色器vertexshader里面用代码控制的

```
' if(Vertex.x == 1.0 &&  Vertex.y == 1.0 && Vertex.z == 1.0){ gl_Position = ProjectionMatrix * ModelViewMatrix * vec4(Vertex.x + 1.0, Vertex.y + 1.0, Vertex.z + 1.0,1.0); alpha = 0.0;}',
'else {gl_Position = ProjectionMatrix * ModelViewMatrix * vec4(Vertex,1.0); alpha = 1.0;}',
'  position = ModelViewMatrix * vec4(Vertex.x  ,Vertex.y ,Vertex.z,1.0); ',
```
颜色的变化是在片元着色器fragmentshader里面控制的

```
'  const vec4 diffColor  = vec4(0.5, 0.0, 0.0, 1.0);',
'  const vec4 specColor  = vec4(0.7, 0.7, 0.0, 1.0);',
```
