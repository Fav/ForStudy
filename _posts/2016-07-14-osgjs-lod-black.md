---
layout: post
title: osgb Lod转换成osgjs模型，纹理不显示问题
tags: osgjs问题解决
categories: 经验
---

## 问题描述

**问题：** osgb文件直接转换成osgjs之后，在网页上不显示纹理（不管纹理是否设置，或者纹理图片是否能读取，模型始终是黑色）。只有将osgb先转换成obj，再将obj转换成osgjs，纹理才能显示正常

但是（osgb->obj->osgjs）这种方式生成的成果不能分级显示，而且生成的文件占空间比较大，不利于网络传输
 
[测试工程网址](https://github.com/Fav/learn_osgjs/tree/master/lesson01)

![img]({{"/osgjsLodBlack/image001.png" | prepend: site.imgblog }})

模型格式转换测试

![img]({{"/osgjsLodBlack/image002.png" | prepend: site.imgblog }})

网页显示两种方式获取的osgjs文件效果对比

![img]({{"/osgjsLodBlack/image003.png" | prepend: site.imgblog }})

网页获取纹理图片成功
 
 
 
## 已做测试及对比：

1. 对于（osg->osgjs），删除纹理图片、将纹理图片改为白色、jpg格式换成png格式模型均显示黑色

2. 两个osgjs的主要区别有下面几个地方：

	a) （osg->osgjs）使用pagedlod包装node节点，（osg->obj->osgjs）使用普通node节点包装

	![img]({{"/osgjsLodBlack/image005.png" | prepend: site.imgblog }})

	b) PrimitiveSetList 中DrawElementsUShort 节点的描述（osg->osgjs）使用了一个json对象来描述，而（osg->obj->osgjs）使用了多个json对象描述

	![img]({{"/osgjsLodBlack/image007.png" | prepend: site.imgblog }}) 

	c)（osgb->obj->osgjs）里面的VertexAttributeList 多出一个Normal 节点

	![img]({{"/osgjsLodBlack/image009.png" | prepend: site.imgblog }})

	d) 两个osgjs中的顶点的值的位置不一定一样，有些值是互为负数

	![img]({{"/osgjsLodBlack/image011.png" | prepend: site.imgblog }})


## 最终处理方案：

***将（osgb->obj->osgjs）中的“Normal”节点信息，插入到(osgb->osgjs)的对应位置，这应该是osgjs插件的bug***
