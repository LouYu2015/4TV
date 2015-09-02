# MarkDown格式教程

## 为什么4TV使用MarkDown来记录文档？

我们采用MarkDown格式是因为它便于我们进行文档管理。一份使用 Markdown 格式撰写的文件可以直接以纯文本方式编写和发布，并且这种格式很容易记忆和阅读。而它在转换成html以后排版也很整齐。这个文档就是用MarkDown格式编写的。此外，纯文本也便于Git对我们电视台的文档版本进行记录。

下面，就让我们开始了解MarkDown的格式吧。

## 区块元素
### 段落和换行
一个 Markdown 段落由一个或多个连续的行组成。两个段落之间必须有一个以上的空行，否则会被视为同一个段落（空行的定义是显示时看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行）。

段落不能用空格或制表符来缩进，因为这有其他的含义。

### 标题
Markdown 支持两种标题的语法，类 Setext 和类 atx 式。

类 Setext 形式是利用 = （最高阶标题）和 - （第二阶标题）做成底线的样子，例如：

```
This is an H1
=============

This is an H2
-------------
```

任何数量的 = 和 - 都可以有效果。

类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到 1 到 6 等级的标题，例如：

```
# 这是 H1

## 这是 H2

###### 这是 H6
```

你可以选择性地「闭合」类 atx 样式的标题，即在行尾也加上 #，而行尾的 # 数量也不用和开头一样（只有行首的井字符数量会决定标题的阶数）：

```
# 这是 H1 #

## 这是 H2 ##

### 这是 H3 ######
```

### 区块引用Blockquotes
Markdown 标记区块引用是使用类似 email 中用 > 的引用方式。在每行的最前面加上`>`即可：

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

显示时，左面会出现一个竖线来表示引用。

区块引用可以嵌套（例如引用中已经有了引用的时候），只要根据层次加上不同数量的 > ：

```
> 这是第一级引用
>
> > 这是第二级引用
>
> 回到第一级
```

多级引用显示时会有多个竖线来区分层次。

引用的区块内也可以包含其他的 Markdown 语法，包括标题、列表等。它们都会按照相应的格式显示：

```
> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
```

### 列表
Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为项目标记，项目标记后面则一定要接着至少一个空格或制表符：

```
*   Red
*   Green
*   Blue
```

等同于：

```
+   Red
+   Green
+   Blue
```

也等同于：

```
-   Red
-   Green
-   Blue
```

有序列表则使用数字接着一个英文句点：

```
1.  Bird
2.  McHale
3.  Parish
```

很重要的一点是，你在列表标记上使用的编号并不会影响显示的编号。MarkDown总会按照正确的编号来进行显示，不管你写的编号是什么。

如果你的列表标记写成：

```
1.  Bird
1.  McHale
1.  Parish
```

或甚至是：

```
3. Bird
1. McHale
8. Parish
```

你都会得到完全相同的结果。

列表项目标记通常是放在最左边，但是其实也可以缩进，最多 3 个空格：

```
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.
```

列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符，否则将会被当成普通段落，导致后面的项目编号重新开始：

```
1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
```

如果要在列表项目内放进引用，那`>`也需要缩进：

```
*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.
```

当然，项目列表很可能会不小心产生，像是下面这样的写法

```
1986. What a great season.
```

在行首出现数字-句点-空白的形式时，会被误以为是项目标记。要避免这样的状况，你可以在句点前面加上反斜杠，以明确的表示这只是个普通的句点而不是格式标记，具体参见 `其他` 标题下的 `反斜杠` 栏目：

```
1986\. What a great season.
```

### 分隔线
你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

```
* * *
```

```
***
```

```
*****
```

```
- - -
```

```
---------------------------------------
```

## 区段元素
### 链接
Markdown 支持两种形式的链接语法： 行内式和参考式。

不管是哪一种，链接文字都是用 [方括号] 来标记。

要建立一个行内式的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的提示文字，只要在网址后面，用双引号把提示文字包起来即可，例如：

```
这是一个[示例](http://example.com/ "提示文字")链接.

[这个链接](http://example.net/)没有特别的提示文字。
```

提示文字是用于鼠标悬停的时候显示提示条的。

你可以使用相对路径，即省略项目所在的路径（例如省略4tv文档库所在路径，直接从文档库的目录开始写）：

```
See my [About](about/) page for details.
```

此时不要在链接前添加斜杠。

参考式的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

```
This is [an example][id] reference-style link.
```

你也可以选择性地在两个方括号中间加上一个空格：

```
This is [an example] [id] reference-style link.
```

接着，在文件的任意处，你可以把这个标记的链接内容定义出来：

```
[id]: http://example.com/  "Optional Title Here"
```

链接内容定义的形式为：

* 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
* 接着一个冒号
* 接着一个以上的空格或制表符
* 接着链接的网址
* 选择性地接着 title 内容，可以用单引号、双引号或是括弧包着

下面这三种链接的定义都是相同：

```
[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)
```

网址定义只是用于指定链接内容，不会被显示出来。

链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写，因此下面两个链接是一样的：

```
[link text][a]
[link text][A]
```

有时用隐式链接标记会比较方便。在链接文字后面加上一个空的方括号即表示id与链接文字本身相同。如果你要让 "Google" 链接到 google.com，你可以简化成：

```
[Google][]
```

然后定义链接内容：

```
[Google]: http://google.com/
```

链接的定义可以放在文件中的任何一个地方，例如放在文件最后面，就像是注解一样。

下面是一个参考式链接的范例：

```
I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
```

或者用链接名称的方式写：

```
I get 10 times more traffic from [Google][] than from
[Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"
```

下面是用行内式写的同样一段内容的 Markdown 文件，提供作为比较之用：

```
I get 10 times more traffic from [Google](http://google.com/ "Google")
than from [Yahoo](http://search.yahoo.com/ "Yahoo Search") or
[MSN](http://search.msn.com/ "MSN Search").
```

参考式的链接其实重点不在于它比较好写，而是它比较好读，比较一下上面的范例，使用参考式的文章段落本身只有 81 个字符，但是用行内形式的却会增加到 176 个字符，阅读时显得十分臃肿。所以，使用 Markdown 的参考式链接，可以让你可以把一些标记相关的数据移到段落文字之外，让文件更像是浏览器最后产生的结果，避免阅读的感觉被打断。

### 强调
Markdown 使用星号（`*`）和底线（`_`）作为标记强调字词的符号，被 `*` 或 `_` 包围的字词会被转成斜体，用两个 `*` 或 `_` 包起来的话，则会被转成粗体，例如：

```
*斜体*

_斜体_

**粗体**

__粗体__
```

你可以随便用你喜欢的样式，唯一的限制是，你开始用什么符号，就要用什么符号结束。

强调也可以直接插在文字中间：

```
un*frigging*believable
```

但是如果你的 `*` 和 `_` 两边都是空白的话，它们就只会被当成普通的符号。

### 代码
电视台的文档中通常不需要代码。但是我们也可以用这个来标记引用的话语。如果要标记一小段行内代码，你可以用反引号把它包起来（` ` `），例如：

```
Use the `printf()` function.
```

大概就是这样的效果：`printf()`

如果要在区段内包含反引号，你可以用多个反引号来表示开启和结束代码区段：

```
``There is a literal backtick (`) here.``
```

这样只有遇到与开头反引号数量相同的连续反引号才会被认为是区块的结束。

代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样你就可以在区段的一开始就插入反引号：

```
A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``
```

此外，你还可以在每个段落的开始加上4个空格或者1个制表符缩进，表示一大块区块：

```
	第一行
	第二行
	第三行
```

或者三个以上的反引号：

````
```
第一行
第二行
第三行
```
````

效果就和你看到的所有格式示例一样，会被用框子圈起来。

### 图片
Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。

行内式的图片语法看起来像是：

```
![替代文字](路径/图片.jpg)

![替代文字](路径/图片.jpg "提示文字")
```

当图片无法显示时，替代文字会用于替代图片。建议在替代文字中写个图片的简短标题，这样图片无法加载时对文章的阅读影响会小一些。

详细的格式叙述如下：

* 一个惊叹号 `!`
* 接着一个方括号，里面放上图片的替代文字
* 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的提示文字。

参考式的图片语法则长得像这样：

```
![替代文字][id]
```

「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：

```
[id]: url/to/image  "Optional title attribute"
```

## 其它
### 反斜杠
Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号，例如：如果你想显示星号而不是表示强调，你可以在星号的前面加上反斜杠：

```
\*literal asterisks\*
```

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

```
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号
```

### 自动链接
Markdown 支持以比较简洁的自动链接形式来处理网址和电子邮件信箱，只要是用方括号包起来， Markdown 就会自动把它转成链接。链接文字默认和链接地址一样，例如：

```
<http://example.com/>
```

邮址的自动链接也很类似，例如：

```
<address@example.com>
```

会变成发送邮件的链接（打开时浏览器的处理方式一般是打开Outlook之类的邮件管理软件）。

## 结语

到这里本教程就结束了。希望这个教程能够帮助你高效的使用MarkDown这个工具。

当然，虽然MarkDown的格式设计的非常符合正常的书写习惯，比较容易记忆，但也不是马上就能记住的。在此我推荐 `MarkdownPad 2` 这个软件（网上有破解版），可以在编辑的同时提供效果预览，便于大家通过实践来进行学习。当然，现在MarkDown的工具也很多，你也可以尝试其他的软件。

最后，虽然本教程已经覆盖了大部分MarkDown格式知识，但这也只是格式。我们电视台还制定了[4tv文档编写指南][]为大家的文档形式提供指导。

## 扩展链接

[4tv文档编写指南]
