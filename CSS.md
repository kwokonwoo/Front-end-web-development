![A CSS rule-set](https://github.com/kwokonwoo/Front-end-web-development/blob/master/images/selector.gif)

The CSS element Selector based on the element name. 

The CSS id Selector is used to select one unique element.(Note: An id name cannot start with a number!)

The CSS class Selector: `.center{}`、`p.center{}`, HTML elements can also refer to more than one class: `<p class="center large">paragraph</p>`. In the example the `<p>` element will be styled according to `class="enter"` and to `class="large"`. (Note: A class name cannot start with a number!)

The CSS id Selector and the Class Selector 不同之一在于一个HTML元素只能有一个CSS id却可以有多个Class. 

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

`font`声明中唯一允许使用斜线分割关键字的地方是设置元素的字体大小和行高：
```
h2 {
  font: large/150% sans-serif;
}
```

使用属性和值选择元素时需要属性值的精准匹配，这与点-类选择（`.class`）是不等同的。

CSS Selectors level 4 为属性选择器引入了忽略大小写选项。在中括号关闭之前使用i允许选择器匹配属性值的时候忽略大小写，无视文档语言的规则。
```
a[herf$='.PDF' i]
```
/* 以上示例适用于不确定是.pdf、.PDF还是.Pdf的情况；建议在任何情况下都为属性选择器中的属性值添加引号，尽管只有非法标识符导致它需要被标记成字符串的时候引号才是必需的。 */

是否在元素和属性语法中强制区分大小写是由语言决定的，XHTML是大小写敏感的语言，而HTML5则是大小写不敏感的语言。

选择子元素而不是任意后代元素：
```
h1 > strong{
  color: red;
}
```

Top and bottom margins of elements are sometimes collapsed into a single margin that is equal to the largest of the two margins.(This does not happen on left and right margins.)

如果多于一个规则指定了相同的属性值都应用到一个元素上，CSS规定拥有更高确定度的选择器优先级更高。ID选择器比类选择器更具确定度, 而类选择器比标签选择器（tag selector）更具确定度。如果样式中包含冲突的规则，且它们具有相同的确定度。那么，后出现的规则优先级高。

`inline-block`的元素（如`input`、`img`）既具有`block`元素可以**设置宽高的特性**，同时又具有`inline`元素默认不换行的特性。
