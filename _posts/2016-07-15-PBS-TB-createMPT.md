---
layout: post
title: 使用PortableBasemapServer 和 terrabuilder 制作MPT --以太原市为例
tags: skyline PortableBasemapServer pbs terrabuilder MPT 
categories: 经验 教程
---

PortableBasemapServer [下载地址]( http://geopbs.codeplex.com/){:target="_blank"}

### 下载数据
1. 打开PortableBasemapServer   
![img]({{"/2016-07-15-PBS-TB-createMPT/image001.png" | prepend: site.imgblog }})

2. 选择【格式转换 】-【在线地图->MBTiles】

3. 在数据源类型中选择自己需要的项，找到要下载区域，“按下并”拖动鼠标右键绘制下载范围（这里我选择的是bing地图，图上没有标注，找目的地时可以打开网页百度地图参考位置）  
![img]({{"/2016-07-15-PBS-TB-createMPT/image002.png" | prepend: site.imgblog }})

4. 点击【开始】按钮，进行下载

### 发布数据

1. 在PortableBasemapServer 主界面中的【数据源类型】下拉列表中选择【MBTiles】,【数据源路径】选择刚才下载的 .mbtiles 文件  
![img]({{"/2016-07-15-PBS-TB-createMPT/image003.png" | prepend: site.imgblog }})

1. 点击创建新服务(双击生成的服务，可以预览地图)，拷贝【OGC WMTS URL】备用    
![img]({{"/2016-07-15-PBS-TB-createMPT/image004.png" | prepend: site.imgblog }})  
![img]({{"/2016-07-15-PBS-TB-createMPT/image005.png" | prepend: site.imgblog }})  

到这里，pbs的设置告一段落

### 使用terrabuilder 生成MPT

1.  创建一个Globe project 工程  
![img]({{"/2016-07-15-PBS-TB-createMPT/image006.png" | prepend: site.imgblog }})  

1.  插入图层  
![img]({{"/2016-07-15-PBS-TB-createMPT/image007.png" | prepend: site.imgblog }})  
![img]({{"/2016-07-15-PBS-TB-createMPT/image008.png" | prepend: site.imgblog }})  
![img]({{"/2016-07-15-PBS-TB-createMPT/image009.png" | prepend: site.imgblog }})  
![img]({{"/2016-07-15-PBS-TB-createMPT/image010.png" | prepend: site.imgblog }})  

1. 开始创建MPT  
![img]({{"/2016-07-15-PBS-TB-createMPT/image011.png" | prepend: site.imgblog }})  
![img]({{"/2016-07-15-PBS-TB-createMPT/image012.png" | prepend: site.imgblog }})  

1. 创建完成后，会在相应目录下生成 mpt文件，可以在 TerraExplorer中打开
![img]({{"/2016-07-15-PBS-TB-createMPT/image013.png" | prepend: site.imgblog }})  


### 最终效果展示（这里用mpt叠加倾斜摄影成果）  
![img]({{"/2016-07-15-PBS-TB-createMPT/image014.png" | prepend: site.imgblog }})    

![img]({{"/2016-07-15-PBS-TB-createMPT/image015.png" | prepend: site.imgblog }})    
