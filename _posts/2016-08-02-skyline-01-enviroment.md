---
layout: post
title: Skyline web开发教程01-环境部署
tags: Skyline web开发教程
categories: Skyline web开发教程
---

## 环境部署

### 单机环境：

- 浏览器： 只支持IE (推荐 ie 9.0 及以上版本)
- 软件: TerraExplorer Pro Plus v6.6.1 English(需要授权)
- 数据：可浏览的 fly文件

### 服务器部署

- 软件：TerraGate 安装包

- 注意事项：

安装之前，先把从官方获取的lic文件（SLFeatureServer.lic 和 SLTerraGate.lic）放到安装目录中，再开始安装，不然有可能出现服务无法启动，或者TerraGate SFS Administration无法进入登录界面的问题

terrain service 的端口最好改一下（默认是80），改成81，或者没有使用的

有些软件会占用 443 端口（svn服务器等），也会造成terrain service无法启动


### 代码下载

链接: [https://pan.baidu.com/s/1mi6Nzle](https://pan.baidu.com/s/1mi6Nzle){:target="_blank"} 密码: ekhu


注： 做skyline web开发最好对TerraExplorer 软件有一定的了解 ,很多三维球初始化的工作都可以在fly文件里面配置，比如初始化位置，视角，是否显示屏幕中心十字丝...等等