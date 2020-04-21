超文本有两层含义：It defines the meaning and structure of web content.

（1）超出文本的限制，即图片、音频、视频、多媒体等内容。

（2）从一个文件跳转到另一个文件，与世界各地主机的文件进行连接，即超级链接文本。

HTML作为一种标记语言与编程语言的不同之处在于标记语言没有编译过程，HTML标签直接由浏览器解析执行。

**`<h1>`的标签有什么用？**
- True: 给文本增加主标题的语义。
- False: ~~给文字加粗、加黑、变大~~。

HTML was created to **describe the content** of a web page, like:

`<h1>This is a heading</h1>`

`<p>This is a paragraph.</p>`

**元素**：e.g., `<p>body</p>`称为元素。

**HTTP**：超文本传输协议。SMTP：邮件传输协议；FTP：文件传输协议。

在文件里输入`html:5`再按一下`Tab`键，可以自动生成html页面的骨架。添加超链接的形如：`<a href="https://www.google.com">Google</a>`

`<p></p>`用来定义一段文字，不与这段文字在一起的都会开启新的行。

The name of an element inside a tag is case insensitive. For example, the `<title>` tag can be written as `<Title>`, `<TITLE>`, or in any other way.

![Anatomy of an HTML element](https://github.com/kwokonwoo/Front-end-web-development/blob/master/images/grumpy-cat-small.png)

**Nesting elements**`: <p>My cat is <strong>very</strong> grumpy. </p>`

一些缩写的含义：
- **src** = **s**ou**rc**e
- **alt** = **alt**ernative
- **a** = **a**nchor
- **href** = **h**ypertext **ref**erence
- **ul** = **u**nodered **l**ists
- **ol** = **o**dered **l**ists

`<a>`中可以添加attribute `target="_blank"`使得链接在新的标签页打开。

![Anatomy of a CSS ruleset](https://github.com/kwokonwoo/Front-end-web-development/blob/master/images/css-declaration-small.png)

`<video>`中可以添加的attribute有`loop`(播完循环播放),`controls`(显示控件）,`poster=""`（添加封面）等，YouTube分享中自带embed可以直接复制视频到网页，如：

  `<iframe width="560" height="315" src="https://www.youtube.com/embed/pQN-pnXPaVg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`

Browsers will apply some **default styling** to the `<h1>` element(among others), that's because we want even an unstyle webpage to have basic readability. To get rid of the gap because of the default styling, we overrode the default styling by setting `margin: 0`.
