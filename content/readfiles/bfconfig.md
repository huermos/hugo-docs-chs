## Blackfriday配置

`taskLists`
: 默认值：`true`<br>
  变量名：<br>
  作用：`false`会停用生成GitHub风格的自动任务列表。

`smartypants`
: 默认值：`true`<br>
  变量名：`HTML_USE_SMARTYPANTS`<br>
  作用：`false`会禁用智能标点符号替换，包括引号，破折号和分数等。启用（`true`）后则可以使用`angledQuotes`，`fractions`，`smartDashes`和`latexDashes`进行微调（见下文）。

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
  作用：`false`会禁用智能破折号。例如，会将连字符（-）转换为en破折号（–）或em破折号（—）。启用（`true`）后可以使用`latexDashes`进行微调（见下文）。

`latexDashes`
: default: **`true`** <br>
    Blackfriday flag: **`HTML_SMARTYPANTS_LATEX_DASHES`** <br>
    Purpose: `false` disables LaTeX-style smart dashes and selects conventional smart dashes. Assuming `smartDashes`: <br>
    If `true`, `--` is translated into &ndash; (`&ndash;`), whereas `---` is translated into &mdash; (`&mdash;`). <br>
    However, *spaced* single hyphen between two words is translated into an en&nbsp;dash&mdash; e.g., "`12 June - 3 July`" becomes `12 June &ndash; 3 July` upon rendering.

`hrefTargetBlank`
: default: **`false`** <br>
    Blackfriday flag: **`HTML_HREF_TARGET_BLANK`** <br>
    Purpose: `true` opens external links in a new window or tab.

`plainIDAnchors`
: default **`true`** <br>
    Blackfriday flag: **`FootnoteAnchorPrefix` and `HeaderIDSuffix`** <br>
    Purpose: `true` renders any heading and footnote IDs without the document ID. <br>
    Example: renders `#my-heading` instead of `#my-heading:bec3ed8ba720b970`

`extensions`
: default: **`[]`** <br>
    Purpose: Enable one or more Blackfriday's Markdown extensions (**`EXTENSION_*`**). <br>
    Example: Include `hardLineBreak` in the list to enable Blackfriday's `EXTENSION_HARD_LINE_BREAK`. <br>
    *See [Blackfriday extensions](#blackfriday-extensions) section for information on all extensions.*

`extensionsmask`
: default: **`[]`** <br>
    Purpose: Disable one or more of Blackfriday's Markdown extensions (**`EXTENSION_*`**). <br>
    Example: Include `autoHeaderIds` as `false` in the list to disable Blackfriday's `EXTENSION_AUTO_HEADER_IDS`. <br>
    *See [Blackfriday extensions](#blackfriday-extensions) section for information on all extensions.*

## Blackfriday extensions

`noIntraEmphasis`
: default: *enabled* <br>
    Purpose: The "\_" character is commonly used inside words when discussing
    code, so having Markdown interpret it as an emphasis command is usually the
    wrong thing.  When enabled, Blackfriday lets you treat all emphasis markers
    as normal characters when they occur inside a word.

`tables`
: default: *enabled* <br>
    Purpose: When enabled, tables can be created by drawing them in the input
    using the below syntax:
    Example:

           Name | Age
        --------|------
            Bob | 27
          Alice | 23

`fencedCode`
: default: *enabled* <br>
    Purpose: When enabled, in addition to the normal 4-space indentation to mark
    code blocks, you can explicitly mark them and supply a language (to make
    syntax highlighting simple).

    You can use 3 or more backticks to mark the beginning of the block, and the
    same number to mark the end of the block.

    Example:

         ```md
        # Heading Level 1
        Some test
        ## Heading Level 2
        Some more test
        ```

`autolink`
: default: *enabled* <br>
    Purpose: When enabled, URLs that have not been explicitly marked as links
    will be converted into links.

`strikethrough`
: default: *enabled* <br>
    Purpose: When enabled, text wrapped with two tildes will be crossed out. <br>
    Example: `~~crossed-out~~`

`laxHtmlBlocks`
: default: *disabled* <br>
    Purpose: When enabled, loosen up HTML block parsing rules.

`spaceHeaders`
: default: *enabled* <br>
    Purpose: When enabled, be strict about prefix header rules.

`hardLineBreak`
: default: *disabled* <br>
    Purpose: When enabled, newlines in the input translate into line breaks in
    the output.


`tabSizeEight`
: default: *disabled* <br>
    Purpose: When enabled, expand tabs to eight spaces instead of four.

`footnotes`
: default: *enabled* <br>
    Purpose: When enabled, Pandoc-style footnotes will be supported.  The
    footnote marker in the text that will become a superscript text; the
    footnote definition will be placed in a list of footnotes at the end of the
    document. <br>
    Example:

        This is a footnote.[^1]

        [^1]: the footnote text.

`noEmptyLineBeforeBlock`
: default: *disabled* <br>
    Purpose: When enabled, no need to insert an empty line to start a (code,
    quote, ordered list, unordered list) block.


`headerIds`
: default: *enabled* <br>
    Purpose: When enabled, allow specifying header IDs with `{#id}`.

`titleblock`
: default: *disabled* <br>
    Purpose: When enabled, support [Pandoc-style title blocks][1].

`autoHeaderIds`
: default: *enabled* <br>
    Purpose: When enabled, auto-create the header ID's from the headline text.

`backslashLineBreak`
: default: *enabled* <br>
    Purpose: When enabled, translate trailing backslashes into line breaks.

`definitionLists`
: default: *enabled* <br>
    Purpose: When enabled, a simple definition list is made of a single-line
    term followed by a colon and the definition for that term. <br>
    Example:

        Cat
        : Fluffy animal everyone likes

        Internet
        : Vector of transmission for pictures of cats

    Terms must be separated from the previous definition by a blank line.

`joinLines`
: default: *enabled* <br>
    Purpose: When enabled, delete newlines and join the lines.

[1]: http://pandoc.org/MANUAL.html#extension-pandoc_title_block
