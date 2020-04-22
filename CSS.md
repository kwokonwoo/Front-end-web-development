![A CSS rule-set](https://github.com/kwokonwoo/Front-end-web-development/blob/master/images/selector.gif)

The CSS element Selector based on the element name. 

The CSS id Selector is used to select one unique element.(Note: An id name cannot start with a number!)

The CSS class Selector: `.center{}`、`p.center{}`, HTML elements can also refer to more than one class: `<p class="center large">paragraph</p>`. In the example the `<p>` element will be styled according to `class="enter"` and to `class="large"`. (Note: A class name cannot start with a number!)

The CSS Universal Selector (*) selects all HTML elements on the page.

The CSS Grouping Selector就是选择具有相同style definitions的HTML元素，如选择具有相同定义的h1，h2，p CSS codes可以写成`h1, h2, p {}`.

在有多重样式表（Style Sheet）定义下，最后被读取的值将会被使用，即哪个在后面哪个将被读取。例：
```
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
<style>
h1 {
  color: orange;
  }
</style>
</head>
```

上例中`<h1>`elements将是"orange".

**What style will be used when there is more than one style specofied for an HtMl element?**
All the styles in a page will "cascade" into a new "**virtual**" style sheet by the following rules, where number one has the hightest priority:
- Inline style(inside an HTML element)
- External and internal style sheets(in the head section: 取决于哪个在后面)
- Browser default

[Opacity / Transparency](https://www.w3schools.com/code/tryit.asp?filename=GE3CC81ZCQ6I)

即便`link`tag中链接到CSS声明中包含了`type="text/css"`，还是需要在样式表加上后缀`.css`，这是因为一些老的浏览器无法识别后缀不为.css的样式表文件。

