---
layout: post
title: Lesson03-节点查找
tags: osgjs
categories: osgjs官方教程笔记
---


[官方效果展示](http://codepen.io/osgjs/pen/GsAzw)

这一节看上去也有很多熟悉的地方，整理一下思路:
1. 获取canvas

2. 创建一个平移([-5,10,-5])的矩阵平移对象，并设置名字为'BoxRotate'

3. 创建一个立方体，中心点为[0,0,0],长宽高分别为[5,5,5],并进行选装，设置状态

4. 创建一个Node，设置名字为'Light.003',并设置灯光

5. 创建一个类FindByNameVisitor 继承osg.NodeVisitor，模式设置为访问所有节点

6. 通过名字进行对象的查找，

7. 将查找结果显示在界面上，并输出到命令行

## 知识点

###  查找

```
// Here we create a new form of
// Scene Graph Visitor
var FindByNameVisitor = function ( name ) {
    osg.NodeVisitor.call( this, osg.NodeVisitor.TRAVERSE_ALL_CHILDREN );
    this._name = name;
};

FindByNameVisitor.prototype = osg.objectInherit( osg.NodeVisitor.prototype, {
    // in found we'll store our resulting matching node
    init: function () {
        this.found = undefined;
    },
    // the crux of it
    apply: function ( node ) {
        if ( node.getName() == this._name ) {
            this.found = node;
            return;
        }
        //继续遍历场景图形剩余的部分
        this.traverse( node );
    }
} );

// we look for a node named 'Light.003'   查找
var finder = new FindByNameVisitor( 'Light.003' );
mainNode.accept( finder );
document.getElementById( 'result_1' ).firstChild.data = finder.found === undefined ? 'No Light.003' : ' found a Light.003 Node';
console.log( finder.found );
```

>缺省情况下，NodeVisitor 基类禁止执行遍历。因此在你的派生类中，需要使用枚举量 NodeVisotor::TRAVERSE_ALL_CHILDREN来初始化基类，以允许执行遍历。否则，OSG 将不会调用用户的apply()方法。 

>如果要使用 NodeVisitor 来遍历整个场景图形，可以将 NodeVisitor 作为Node::accept()的输入参数传递。你可以在任何一个节点上调用 accept()，NodeVisitor 将从那个节点开始遍历整个场景图形。如果要搜索整个场景图形的话，可以从根节点开始调用 accept()。