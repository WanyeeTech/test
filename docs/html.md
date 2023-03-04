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

## 样式规则

### 文件类型

使用HTML5。

HTML5（HTML 语法）是所有HTML文档的首选：`<!DOCTYPE html>`.

（建议使用 HTML，如`text/html`。不要使用XHTML。XHTML，如`application/xhtml+xml`，缺乏浏览器和基础设施支持，并且提供的优化空间小于 HTML。）

尽管HTML允许，但不要关闭void元素，即使用`<br>`而非`<br />`。

### 代码有效性

尽可能使用有效的HTML。

使用有效的HTML代码，除非由于文件大小方面无法实现的性能目标而无法做到这一点。

使用[W3C HTML验证器](https://validator.w3.org/nu/)等工具进行测试。

使用有效的HTML是一个可衡量的基线质量属性，有助于了解技术要求和限制，并确保正确使用HTML。

```html
<!-- 不推荐 -->
<title>Test</title>
<article>This is only a test.

<!-- 推荐 -->
<!DOCTYPE html>
<meta charset="utf-8">
<title>Test</title>
<article>This is only a test.</article>
```

### 语义学

根据其用途使用HTML。

将元素（有时被错误地称为“标签”）用于创建它们的目的。例如，将标题元素用于标题，`p`将元素用于段落，将`a`元素用于锚点等。

根据其用途使用HTML对于可访问性、重用和代码效率方面的原因很重要。

```html
<!-- 不推荐 -->
<div onclick="goToRecommendations();">All recommendations</div>

<!-- 推荐 -->
<a href="recommendations/">All recommendations</a>
```

### 多媒体回退

为多媒体提供替代内容。

对于多媒体，例如图像、视频、动画对象`canvas`，请确保提供替代访问。对于意味着使用有意义的替代文本 (`alt`) 的图像以及视频和音频的文字记录和字幕，如果有的话。

出于可访问性原因，提供替代内容很重要：如果没有 ，盲人用户几乎没有什么线索可以判断图像的内容`@alt`，而其他用户可能无法理解视频或音频内容的内容。

（对于其`alt`属性会引入冗余的图像，以及对于您不能立即使用CSS的纯粹装饰目的的图像，请不要使用替代文本，如`alt=""`。）

```html
<!-- 不推荐 -->
<img src="spreadsheet.png">

<!-- 推荐 -->
<img src="spreadsheet.png" alt="Spreadsheet screenshot.">
```

### 关注点分离

将结构与表示与行为分开。

严格地将结构（标记）、表示（样式）和行为（脚本）分开，并尽量将三者之间的交互保持在绝对最低限度。

也就是说，确保文档和模板仅包含 HTML 和仅用于结构目的的 HTML。将表现形式的所有内容移至样式表，将行为的所有内容移至脚本中。

此外，通过从文档和模板链接尽可能少的样式表和脚本，使接触区域尽可能小。

出于维护原因，将结构与表示与行为分开很重要。更改 HTML 文档和模板总是比更新样式表和脚本更昂贵。

```html
<!-- 不推荐 -->
<!DOCTYPE html>
<title>HTML sucks</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I’ve read about this on a few sites but now I’m sure:
  <u>HTML is stupid!!1</u>
<center>I can’t believe there’s no way to control the styling of
  my website without doing everything all over again!</center>

<!-- 推荐 -->
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">
<h1>My first CSS-only redesign</h1>
<p>I’ve read about this on a few sites but today I’m actually
  doing it: separating concerns and avoiding anything in the HTML of
  my website that is presentational.
<p>It’s awesome!
```

### 实体引用

不要使用实体引用。

假设相同的编码 (UTF-8) 用于文件和编辑器以及团队之间，则无需使用`&mdash;`、`&rdquo;`、`&#x263a;`。

唯一的例外适用于 HTML 中具有特殊含义的字符（如`<`和`&`）以及控制或“不可见”字符（如不间断空格）。

```html
<!-- 不推荐 -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.

<!-- 推荐 -->
The currency symbol for the Euro is “€”.
```

### 可选标签

省略可选标签（可选）。

出于文件大小优化和可扫描性目的，请考虑省略可选标签。HTML5规范定义了哪些标签可以省略。

（这种方法可能需要一个宽限期来建立一个更广泛的指导方针，因为它与网络开发人员通常被教导的有很大不同。出于一致性和简单性的原因，最好省略所有可选标签，而不仅仅是一个选择。）

```html
<!-- 不推荐 -->
<!DOCTYPE html>
<html>
  <head>
    <title>Spending money, spending bytes</title>
  </head>
  <body>
    <p>Sic.</p>
  </body>
</html>

<!-- 推荐 -->
<!DOCTYPE html>
<title>Saving money, saving bytes</title>
<p>Qed.
```

### `type`属性

省略`type`样式表和脚本的属性。

不要将`type`属性用于样式表（除非不使用CSS）和脚本（除非不使用JavaScript）。

在这些上下文中指定`type`属性不是必需的，因为HTML5使用`text/css`和`text/javascript`作为默认值。即使对于较旧的浏览器，也可以安全地完成此操作。

```html
<!-- 不推荐 -->
<link rel="stylesheet" href="https://www.google.com/css/maia.css" type="text/css">

<!-- 推荐 -->
<link rel="stylesheet" href="https://www.google.com/css/maia.css">
```

```html
<!-- 不推荐 -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js" type="text/javascript"></script>

<!-- 推荐 -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
```

### `id`属性

避免不必要的`id`属性。

首选`class`样式属性和`data`脚本属性。

在严格要求属性的情况下`id`，始终在值中包含连字符以确保它不匹配 JavaScript 标识符语法，例如使用`user-profile`而不是`profileor`或`userProfile`。

当元素具有属性时，浏览器会将其作为[全局原型id上的命名属性](https://html.spec.whatwg.org/multipage/nav-history-apis.html#named-access-on-the-window-object)，这可能会导致意外行为。虽然包含连字符的属性值仍可用作属性名称，但这些不能作为全局 JavaScript变量引用。

```html
<!-- 不推荐：`window.userProfile` 将解析为引用 <div> 节点 -->
<div id="userProfile"></div><div id="userProfile"></div>
```

```html
<!-- 推荐：`id` 属性是必需的，它的值包括一个连字符 -->
<div aria-describedby="user-profile"><div aria-describedby="user-profile">
  …
  <div id="user-profile"></div><div id="user-profile"></div>
  …
</div></div>
```

## 格式规则

### 通用格式

为每个块、列表或表元素使用一个新行，并缩进每个这样的子元素。

独立于元素的样式（因为CSS允许元素为每个属性承担不同的角色`display`），将每个块、列表或表格元素放在一个新行上。

此外，如果它们是块、列表或表元素的子元素，则缩进它们。

（如果您在列表项之间遇到空格问题，可以将所有`li`元素放在一行中。鼓励linter抛出警告而不是错误。）

```html
<blockquote>
  <p><em>Space</em>, the final frontier.</p>
</blockquote>
```

```html
<ul>
  <li>Moe
  <li>Larry
  <li>Curly
</ul>
```

```html
<table>
  <thead>
    <tr>
      <th scope="col">Income
      <th scope="col">Taxes
  <tbody>
    <tr>
      <td>$ 5.00
      <td>$ 4.50
</table>
```

### 换行

打断长行（可选）。

虽然没有针对HTML的列限制建议，但如果可以显着提高可读性，您可以考虑换行。

换行时，每个续行应从原始行至少缩进4个额外的空格，以区分换行的属性和子元素。

```html
<button mat-icon-button color="primary" class="menu-button"
    (click)="openMenu()">
  <mat-icon>menu</mat-icon>
</button>
```

```html
<button
    mat-icon-button
    color="primary"
    class="menu-button"
    (click)="openMenu()">
  <mat-icon>menu</mat-icon>
</button>
```

```html
<button mat-icon-button
        color="primary"
        class="menu-button"
        (click)="openMenu()">
  <mat-icon>menu</mat-icon>
</button>
```

### 引号

引用属性值时，请使用双引号。

在属性值周围使用双引号 (`""`) 而不是单引号 (`''`)。

```html
<!-- 不推荐 -->
<a class='maia-button maia-button-secondary'>Sign in</a>

<!-- 推荐 -->
<a class="maia-button maia-button-secondary">Sign in</a>
```
