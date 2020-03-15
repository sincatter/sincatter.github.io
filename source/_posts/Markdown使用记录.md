---
title: Markdown使用记录
tags:
  - 备忘
  - markdown
  - 操作
categories:
  - 备忘
toc: false
date: 2020-03-15 23:04:35
---

## 图片
```
![替代字符](图片地址 "标题")
```
标准的Markdown图片使用包含三个属性:替代字符、图片地址、图片标题。  
其中:替换字符是指当图片不可见时显示的字符，标题则是指鼠标放置与图片上显示的标题，三者均可为空。  
特殊情况下存在对图片尺寸自定义及居中等需求，可以尝试直接使用html嵌套。  
例如，如下表示宽度10%，居中放置：
```
<img src="https://gitee.com/sincatter/open_resources/raw/picture/static/muniulogo.png" width="10%" align="center">
```
<img src="https://gitee.com/sincatter/open_resources/raw/picture/static/muniulogo.png" width="10%" align="center">