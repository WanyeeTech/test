---
layout: default
title: CSS风格指南
---

## 样式规则

### 协议

尽可能对嵌入式资源使用 HTTPS。

始终对图像和其他媒体文件、样式表和脚本使用 HTTPS (`https:`)，除非相应文件无法通过 HTTPS 访问。

```css
/* 不推荐：省略协议 */
@import '//fonts.googleapis.com/css?family=Open+Sans';

/* 不推荐：使用 HTTP */
@import 'http://fonts.googleapis.com/css?family=Open+Sans';.min.js"></script>

/* 推荐 */
@import 'https://fonts.googleapis.com/css?family=Open+Sans';
```

## 排版规则

### 缩进

每次缩进 2 个空格。

不要使用制表符或混用制表符和空格进行缩进。

```css
.example {
  color: blue;
}
```

### 大小写

只用小写字母。

所有代码都必须是小写的：这适用于 HTML 元素名称、属性、属性值（`text/CDATA`除外）、CSS 选择器、属性和属性值（字符串除外）。

```css
/* 不推荐 */
color: #E5E5E5;

/* 推荐 */
color: #e5e5e5;
```

### 行尾空格

删除行尾白空格。
