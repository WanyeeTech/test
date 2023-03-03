---
layout: default
title: HTML风格指南
---

## 样式规则

### 协议

尽可能对嵌入式资源使用 HTTPS。

始终对图像和其他媒体文件、样式表和脚本使用 HTTPS (`https:`)，除非相应文件无法通过 HTTPS 访问。

```html
<!-- 不推荐：省略协议 -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>

<!-- 不推荐：使用 HTTP -->
<script src="http://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>

<!-- 推荐 -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
```

## 排版规则

### 缩进

每次缩进 2 个空格。

不要使用制表符或混用制表符和空格进行缩进。

```html
<ul>
  <li>Fantastic
  <li>Great
</ul>
```

### 大小写

只用小写字母。

所有代码都必须是小写的：这适用于 HTML 元素名称、属性、属性值（`text/CDATA`除外）、CSS 选择器、属性和属性值（字符串除外）。

```html
<!-- 不推荐 -->
<A HREF="/">主页</A><A HREF = "/" >首页</A> 

<!-- 推荐 -->
<img src="google.png" alt="谷歌"><img src = "google.png" alt = "Google" >  
```

### 行尾空格

删除行尾白空格。

```html
<!-- 不推荐 -->
<p>What?_

<!-- 推荐 -->
<p>Yes please.
```
