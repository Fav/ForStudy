---
layout: post
title: OSGJS官方例子使用说明-本机部署
tags: osgjs问题解决
categories: 经验
---

进入 [osgjs官方网站](http://osgjs.org/){:target="_blank"} 点击download 下载最新的包 osgjs-develop.zip 解压到英文目录下

### windws部署到 IIS 下
1. 本机安装 IIS（不会安装请google）

2. 方便起见，这里添加到虚拟目录  
![img]({{"/2016-07-20-run-osgjs-examples/image001.png" | prepend: site.imgblog }})

3. 填好别名和物理路径   
![img]({{"/2016-07-20-run-osgjs-examples/image002.png" | prepend: site.imgblog }})

4. 进入内容视图，随便进入一个例子，在index上点击右键，浏览（建议用chrome或者firefox）   
![img]({{"/2016-07-20-run-osgjs-examples/image003.png" | prepend: site.imgblog }})  
![img]({{"/2016-07-20-run-osgjs-examples/image004.png" | prepend: site.imgblog }})  

5. 发现没显示东西，f12，显示有4个错误，这里需要一个一个解决    
![img]({{"/2016-07-20-run-osgjs-examples/image005.png" | prepend: site.imgblog }})   
![img]({{"/2016-07-20-run-osgjs-examples/image006.png" | prepend: site.imgblog }})  

	(a 找到相关目录，发现bluebird-2.10.2.js 和 hammer-2.0.4.js，这两个js都是带了版本号的，但是html里面没有，建议将这两个文件复制，并去掉版本号  
![img]({{"/2016-07-20-run-osgjs-examples/image007.png" | prepend: site.imgblog }})  

	改为  
![img]({{"/2016-07-20-run-osgjs-examples/image008.png" | prepend: site.imgblog }})    

	(b 本机根本没有builds/dist/OGS.js 这个文件，官方说是需要通过编译获取，如果你不想编译，可以到官方网站的例子里面找到这个文件（新建文件夹builds/dist，打开 http://osgjs.org/builds/dist/OSG.js ，保存到这里）  
![img]({{"/2016-07-20-run-osgjs-examples/image009.png" | prepend: site.imgblog }})

6. 如果出现.osgjs、.json、.glsl等文件出现404不能访问的情况，就需要将它们添加到 MIME中，具体方法如下：
![img]({{"/2016-07-20-run-osgjs-examples/image010.png" | prepend: site.imgblog }})  

	(a 在MIME上点击，
	![img]({{"/2016-07-20-run-osgjs-examples/image011.png" | prepend: site.imgblog }})  

	(b 在空白处点击右键，添加
	![img]({{"/2016-07-20-run-osgjs-examples/image012.png" | prepend: site.imgblog }})  
	![img]({{"/2016-07-20-run-osgjs-examples/image013.png" | prepend: site.imgblog }})  

	(c 保存后刷新网页

7. 这时候网页可以正常显示了