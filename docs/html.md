---
layout: default
title: HTML风格指南
---

## 样式规则

### 协议

尽可能对嵌入式资源使用HTTPS。

始终对图像和其他媒体文件、样式表和脚本使用HTTPS(`https:`)，除非相应文件无法通过HTTPS访问。

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

所有代码都必须是小写的：这适用于HTML元素名称、属性、属性值（`text/CDATA`除外）、CSS选择器、属性和属性值（字符串除外）。

```html
<!-- 不推荐 -->
<A HREF="/">主页</A>

<!-- 推荐 -->
<img src="wanyee.png" alt="万宜">  
```

### 行尾空格

删除行尾白空格。

```html
<!-- 不推荐 -->
<p>What?_

<!-- 推荐 -->
<p>Yes please.
```

## 元数据规则

### 编码

使用UTF-8（无BOM）。

确保您的编辑器使用UTF-8作为字符编码，没有字节顺序标记。

通过指定HTML模板和文档中的编码`<meta charset="utf-8">`。

### 注释

尽可能的去解释你写的代码。

使用注释来解释代码：它涵盖了什么，它的用途是什么，为什么使用或首选各自的解决方案？

（此项是可选的，因为始终要求完整记录代码并不现实。）

### 待办事项

使用`TODO`来标记待办事项和行动项目。

仅使用关键字`TODO`来突出显示待办事项，而不是其他常见格式，如`@@`。

将联系人（用户名或邮件列表）附加到括号中，格式为`TODO(contact)`。

在冒号后附加操作项，如`TODO: action item`。

```html
{# TODO(john.hong)：重审居中标签#}
<center>测试</center>
```
