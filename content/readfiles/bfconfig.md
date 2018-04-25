## Blackfriday配置

`taskLists`
: 默认值：`true`<br>
  变量名：<br>
  作用：`false`会停用生成GitHub风格的自动任务列表。

`smartypants`
: 默认值：`true`<br>
  变量名：`HTML_USE_SMARTYPANTS`<br>
  作用：`false`会禁用智能标点符号替换，包括引号，破折号和分数等。如果为`true`则可以使用`angledQuotes`，`fractions`，`smartDashes`和`latexDashes`进行微调（见下文）。

`smartypantsQuotesNBSP`
: 默认值：`false`<br>
  变量名：`HTML_SMARTYPANTS_QUOTES_NBSP`<br>
  作用：`true`将不会在书名号（French Guillemets，即« »）内插入空格。

`angledQuotes`
: 默认值：`false`<br>
  变量名：`HTML_SMARTYPANTS_ANGLED_QUOTES`<br>
  作用：`true`会自动将引号（" "）渲染为书名号（Angled Double Quotes，即« »）而不是引号（“ ”）。

`fractions`
: 默认值：`true`<br>
  变量名：`HTML_SMARTYPANTS_FRACTIONS`<br>
  作用：`false`会禁用智能分数。<br>
  示例：`5/12`会渲染成<sup>5</sup>&frasl;<sub>12</sub>（&lt;sup&gt;5&lt;/sup&gt;&amp;frasl;&lt;sub&gt;12&lt;/sub&gt;）。**注意**，即使此值为`false`，Blackfriday依然会**仅将**`1/2`，`1/4`，`3/4`三个分数渲染为½，¼，¾。

`smartDashes`
: 默认值：`true`<br>
  变量名：`HTML_SMARTY_DASHES`<br>
  作用：`false`会禁用智能破折号。例如，会将连字符（-）转换为en破折号（–）或em破折号（—）。如果为`true`则可以使用`latexDashes`进行微调（见下文）。

`latexDashes`
: 默认值：`true`<br>
  变量名：`HTML_SMARTYPANTS_LATEX_DASHES`<br>
  作用：`false`会禁用LaTeX风格的智能破折号并使用常规的智能破折号。如果为`true`，`--`会被转换成`–`（en破折号），而`---`会被转换成`—`（em破折号）。不过在两个单词之间且**前后带有空格**的连字符会被渲染为en破折号，例如`12 June - 3 July`会变成`12 June — 3 July`。

`hrefTargetBlank`
: 默认值：`false`<br>
  变量名：`HTML_HREF_TARGET_BLANK`<br>
  作用：`true`会在新窗口或标签页中打开外部链接。

`plainIDAnchors`
: 默认值：`true`<br>
  变量名：`FootnoteAnchorPrefix`和`HeaderIDSuffix`<br>
  作用：`true`在渲染标题和脚注ID时不会带上文档ID。<br>
  示例：`#my-heading`代替`#my-heading:bec3ed8ba720b970`。

`extensions`
: 默认值：`[]`<br>
  作用：启用一个或多个Blackfriday的Markdown扩展（`EXTENSION_*`）。<br>
  示例：在列表中加入`hardLineBreak`来启用Blackfriday的`EXTENSION_HARD_LINE_BREAK`。请参阅[Blackfriday扩展](#blackfriday扩展)。

`extensionsmask`
: 默认值：`[]`<br>
  作用：禁用一个或多个Blackfriday的Markdown扩展（`EXTENSION_*`）。<br>
  示例：在列表中加入`autoHeaderIds`来禁用Blackfriday的`EXTENSION_AUTO_HEADER_IDS`。请参阅[Blackfriday扩展](#blackfriday扩展)。

## Blackfriday扩展

`noIntraEmphasis`
: 默认值：enabled<br>
  作用：在代码中，通常用"\_"书写单词，但Markdown会错误的将其视作强调。启用后，Blackfriday会把单词中的强调标记视作普通字符。

`tables`
: 默认值：enabled<br>
  作用：启用后，可以使用下列语法在来创建表格。<br>
  示例：

```
   Name | Age
--------|------
    Bob | 27
  Alice | 23
```

`fencedCode`
: 默认值：enabled<br>
  作用：启用后，除了用4空格缩进来标记代码块，还可以用直接选择一个语言标记，并直接启用语法高亮。
  示例：

        ```md
        # Heading Level 1
        Some test
        ## Heading Level 2
        Some more test
        ```

`autolink`
: 默认值：enabled<br>
  作用：启用后，即使未被添加超链接的URL地址也会被自动加上链接。

`strikethrough`
: 默认值：enabled<br>
  作用：启用后，双波浪线（`~~`）之间的字符会被加上删除线。<br>
  示例：~~我被删除了~~

`laxHtmlBlocks`
: 默认值：disabled<br>
  作用：启用后，放宽HTML标签的分析规则。

`spaceHeaders`
: 默认值：enabled<br>
  作用：启用后，严格遵守前缀标题规则。

`hardLineBreak`
: 默认值：disabled<br>
  作用：启用后，文本中的换行会在输出时换行。

`tabSizeEight`
: 默认值：disabled<br>
  作用：启用后，Tab为8空格代替4空格。

`footnotes`
: 默认值：enabled<br>
  作用：启用后，将支持Pandoc风格的脚注。文本中的脚注会变成上标文本，脚注定义将被列在文档最后。<br>
  示例：

```
这是脚注[^1]

[^1]: 这就是脚注文本。
```

`noEmptyLineBeforeBlock`
: 默认值：disabled<br>
  作用：启用后，不需要插入空行就可以直接启用（代码，引用，有序列表，无序列表）块。

`headerIds`
: 默认值：enabled<br>
  作用：启用后，允许`{#id}`使用指定标题ID。

`titleblock`
: 默认值：disabled<br>
  作用：启用后，支持[Pandoc风格标题栏](http://pandoc.org/MANUAL.html#extension-pandoc_title_block)。

`autoHeaderIds`
: 默认值：enabled<br>
  作用：启用后，自从创建标题文本（h1至h6）的ID。

`backslashLineBreak`
: 默认值：enabled<br>
  作用：启用后，将尾部的反斜杠转换为换行符。

`definitionLists`
: 默认值：enabled<br>
  作用：启用后，简单的定义列表由单行术语及其冒号后的定义组成。<br>
  示例：

        猫
        : 毛绒绒的可爱动物，人人都爱。

        网络
        : 为云撸猫提供可能性。

两个定义之间必须用一个空行隔开。

`joinLines`
: 默认值：enabled<br>
  作用：启用后，删除换行并加入此行。