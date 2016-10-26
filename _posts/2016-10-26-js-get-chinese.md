---
layout: post
title: js获取URL中传入的中文参数乱码的问题
tags: javascript 中文乱码
categories: javascript经验分享
---

1. URl：http://localhost/whu/info.html?name=四合网吧&address=尖草坪区迎新街东二条&infoid=1&people=2  

2. 使用网上搜索到的正则表达式查找方式  

```
function getQueryString(name) { 
var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)", "i"); 
var r = window.location.search.substr(1).match(reg); 
if (r != null) return unescape(r[2]); return null; 
} 
```  
![img]({{"/2016-10-26-js-get-chinese/1.png" | prepend: site.imgblog }})



### 解决方法
if (r != null) return unescape(r[2]); return null; 中的 unescape 用 decodeURI 替换  
![img]({{"/2016-10-26-js-get-chinese/2.png" | prepend: site.imgblog }})


