---
title: 配置Hugo
linktitle: 配置
description: 如何配置你的Hugo站点。
date: 2018-04-17
translate: 2018-04-18
translator: huermos
weight: 60
---

Hugo使用根目录下的`config.toml`，`config.yaml`或`config.json`文件作为其默认的站点配置文件。

用户也可以选择使用`--config`命令来加载一个或多个站点配置文件。

例如：

```
hugo --config debugconfig.toml
hugo --config a.toml,b.toml,c.toml
```

> 在`--config`中的多个站点文件之间使用半角逗号（,）隔开。

## 所有配置参数

以下是Hugo所使用的配置参数的完整列表，括号内是其默认值。用户可以选择在配置文件中使用或修改这些值。

archetypeDir ("archetypes")
: 放置原型文件（文章模板）的目录。

baseURL
: 主机名（和路径），例如：http://bep.is/ 。

blackfriday
: 请参阅[配置Blackfriday](/getting-started/configuration/#配置Blackfriday)。

buildDrafts (false)
: 在构建时也包括草稿内容。

buildExpired  (false)
: 在构建时也包括已过期的内容。

buildFuture (false)
: 在构建时也包括发布日期之后的内容。

canonifyURLs (false)
: 将相对链接转换为绝对链接。

contentDir ("content")
: 放置文章内容的目录。

dataDir ("data")
: 放置数据文件的目录。

defaultContentLanguage ("en")
: 如果没有指定语言，则默认显示此语言。

defaultContentLanguageInSubdir (false)
: 在子目录中使用默认的文章语言，例如`content/en/`。根目录`/`将会重定向至`/en/`。

disableHugoGeneratorInject (false)
: Hugo在默认情况下，会**仅在站点主页**的HTML头部生成一个meta标签。你可以在这里把他关闭。但我们不希望你这样做，因为这是我们了解Hugo人气上涨的一个途径，十分感谢！

disableKinds ([])
: 禁用**指定类型**的所有页面。可用的值包括：`"page"`, `"home"`, `"section"`, `"taxonomy"`, `"taxonomyTerm"`, `"RSS"`, `"sitemap"`, `"robotsTXT"`, `"404"`。

disableLiveReload (false)
: 禁用浏览器的实时预览。

disablePathToLower (false)
: 不将链接地址转换为小写。

enableEmoji (false)
: 启用Emoji表情支持。请参阅[Emoji表情表](https://www.webpagefx.com/tools/emoji-cheat-sheet/)。

enableGitInfo (false)
: 如果Hugo使用Git进行版本控制，将为每个页面启用`.GitInfo`对象。这会同时更新每个页面最后提交内容的`Lastmod`参数。

enableMissingTranslationPlaceholders (false)
: 如果缺少相应的翻译，则使用占位符代替缺省值或空字符串。

enableRobotsTXT (false)
: 生成`robots.txt`文件。

frontmatter
: 请参阅[配置头文件](#配置头文件)。

footnoteAnchorPrefix ("")
: 脚注锚点的前缀。

footnoteReturnLinkContents ("")
: 脚注链接的显示文本。

googleAnalytics ("")
: Google Analytics的tracking ID。

hasCJKLanguage (false)
: 开启后将在内容中检测是否存在中文，日文和韩文。这会使`.Summary`和`.WordCount`正确运作。

imaging
: 请参阅[图像处理配置](content-management/image-processing/#图像处理配置)。

languages
: 请参阅[配置语言](/content-management/multilingual/#配置语言)。

languageCode ("")
: 站点的语言代码。

disableLanguages
: 请参阅[禁用语言](/content-management/multilingual/#禁用语言)。

layoutDir ("layouts")
: 放置布局（模板）的目录。

log (false)
: 启用日志。

logFile ("")
: 日志文件路径（如果设置了路径将自动启用日志记录）。

menu
: 请参阅[在目录中添加非内容条目](/content-management/menus/#在目录中添加非内容条目)。

metaDataFormat ("toml")
: 元数据的格式。可用的值包括：`"toml"`，`"yaml"`和`"json"`。

newContentEditor ("")
: 创建新内容时使用的编辑器

noChmod (false)
: 不同步文件的权限。

noTimes (false)
: 不同步文件的修改时间。

paginate (10)
: [分页](/templates/pagination/)中每页的默认页数。

paginatePath ("page")
: 分页使用的路径，例如：https://example.com/page/2。

permalinks
: 请参阅[内容管理](/content-management/urls/#固定链接)。

pluralizeListTitles (true)
: 列表中多标题

preserveTaxonomyNames (false)
: 保留分类名称中的特殊字符（"Gérard Depardieu"和"Gerard Depardieu"）。

publishDir ("public")
: Hugo站点生成时的静态文件（HTML等）目录。

pygmentsCodeFencesGuessSyntax (false)
: 当代码块没有指定制定语言时启用语法猜测。

pygmentsStyle ("monokai")
: 语法高亮的主题颜色或样式，请参阅[Pygments主题](https://help.farbox.com/pygments.html)。

pygmentsUseClasses (false)
: 语法高亮使用外部CSS样式。

related
: 请参阅[相关内容](/content-management/related/#配置相关内容)。

relativeURLs (false)
: 启用这个选项后，相对链接的地址会以此文件所在的目录为根目录。注意这并不会影响绝对链接。

rssLimit (unlimited)
: RSS信源（Feed）的最大数量。

sectionPagesMenu ("")
: 请参阅[简单章节目录](/templates/menu-templates/#简单章节目录)

sitemap
: 默认的[网站地图配置](/templates/sitemap-template/#配置-sitemap-xml)。

staticDir ("static")
: 放置静态文件的目录。

stepAnalysis (false)
: 显示程序每一步运行消耗的内存和运行时间。

summaryLength (70)
: 在[`.Summary`](/content-management/summaries/#默认-自动分割)中显示的文本长度。

taxonomies
: 请参阅[配置分类法](/content-management/taxonomies#配置分类法)。

theme ("")
: 使用的主题（保持相同的文件名并放在`/themes/`文件夹下）。

themesDir ("themes")
: 放置主题文件的目录。

title ("")
: 网站标题。

uglyURLs (false)
: 开启后，内容网址将用`/filename.html`代替`/filename/`。

verbose (false)
: 启用详细输出。

verboseLog (false)
: 启用详细日志。

watch (false)
: 监视文件系统的变化，并在需要时重新创建。

> 如果你在类Unix系统上使用Hugo，以下是一个从命令行查找配置选项的快捷方式：

```
cd ~/sites/yourhugosite
hugo config | grep emoji
```

运行后会输出：

```
enableemoji: true
```

## 配置查找顺序

与模板的[查找顺序](/templates/lookup-order/)类似，Hugo也有一个默认的顺序去查找网站目录的配置文件：

1. `./config.toml`
2. `./config.yaml`
3. `./config.json`

在你的`config`文件中，你可以自定义网站的渲染效果，目录和特定参数。

## 示例配置

这是一个配置文件的示例。在`params:`下的值会插入到[模板](/templates/)的[`.Site.Params`](/variables/site/)中。

```
baseURL: "https://yoursite.example.com/"
title: "My Hugo Site"
footnoteReturnLinkContents: "↩"
permalinks:
  post: /:year/:month/:title/
params:
  Subtitle: "Hugo is Absurdly Fast!"
  AuthorName: "Jon Doe"
  GitHubUser: "spf13"
  ListOfFoo:
    - "foo1"
    - "foo2"
  SidebarRecentLimit: 5
```

## 使用环境变量配置

除了上文中提到的三个配置选项外，还可以直接从操作系统的环境变量中定义配置键值。

例如，在类Unix系统中运行以下命令也可以直接设置你的网站标题：

```
$ env HUGO_TITLE="Some Title" hugo
```

因此，如果你使用例如Netlify这样的服务来部署你的网站，这将非常有用。请参阅[Netlify配置文件](https://github.com/gohugoio/hugoDocs/blob/master/netlify.toml)中的示例。

> 当你设置操作系统的环境变量时，配置名必须大写且加上`HUGO_`前缀。

## 在渲染时忽略文件

在`./config.toml`中进行下列设置会使Hugo在渲染时忽略以`.foo`和`.boo`结尾的文件：

```
ignoreFiles = [ "\\.foo$", "\\.boo$" ]
```

这是一个正则表达式。别忘了在TOML中转义反斜杠（`\`）。

## 配置头文件

### 配置日期

日期在Hugo中非常重要，你可以在`config.toml`加入一个`frontmatter`节来指定Hugo如何在内容页面中分配日期。

默认的配置是：

```toml
[frontmatter]
date = ["date","publishDate", "lastmod"]
lastmod = [":git" "lastmod", "date","publishDate"]
publishDate = ["publishDate", "date"]
expiryDate = ["expiryDate"]
```

如果你在部分内容中使用了非标准的日期参数，你可以在`date`中覆盖以下设置：

```toml
[frontmatter]
date = [ "myDate", ":default"]
```

`:default`是默认设置的快捷方式。以上设置会让`.Date`优先选择存在的`myDate`的数据。如果不存在，再从`date`，`publishDate`和`lastmod`中按顺序选择有效日期。

在右边的列表中，只有以":"开头的值具有特殊含义（见下文）。其他的都是在头文件中普通的日期参数（不区分大小写）。还要注意的是Hugo具有一些内置别名：`lastmod`→`modified`，`publishDate`→`pubdate`，`published`与`expiryDate`→`unpublishdate`。因此，在头文件中使用`pubDate`默认会分配给`.PublishDate`。

以下是一些特殊的日期处理：

`:fileModTime`
: 从文件的上次修改日期中获得时间。

例如：

```toml
[frontmatter]
lastmod = ["lastmod" ,":fileModTime", ":default"]
```

这将首先获取头文件中的`lastmod`给`.Lastmod`，然后才尝试查询文件的修改日期。最后，这里的`:default`是不必要的，但是Hugo依然会最后查询`:git`，`date`和`publishDate`中的可用值。

`:filename`
: 从内容文件的文件名中获取日期。例如从`2018-02-22-mypage.md`中获取日期`2018-02-22`。另外，如果你没有设置`slug`，将会把`mypage`带入`.Slug`。

例如：

```toml
[frontmatter]
date  = [":filename", ":default"]
```

这将首先获取文件名中的日期用于`.Date`，然后才尝试查询头文件中的`date`，`publishDate`和`lastmod`。

`:git`
: 这是此内容文件的作者上次git此文件的日期。只有在设置了`--enableGitInfo`或`enableGitInfo = true`时可用。

## 配置Blackfriday

[Blackfriday](https://github.com/russross/blackfriday)是Hugo内置的Markdown渲染引擎。

Hugo默认将Blackfriday配置为更符合常理的参数。

然而，如果你对Markdown有特殊需求，Hugo也公开了一部分Blackfriday行为选项来供你更改。下表列出了与Blackfriday源代码（[html.go](https://github.com/russross/blackfriday/blob/master/html.go)和[markdown.go](https://github.com/russross/blackfriday/blob/master/markdown.go)）所匹配的对应选项：

{{< readfile file="/content/readfiles/bfconfig.md" markdown="true" >}}

{{% note %}}
1. Blackfriday flags are *case sensitive* as of Hugo v0.15.
2. Blackfriday flags must be grouped under the `blackfriday` key and can be set on both the site level *and* the page level. Any setting on a page will override its respective site setting.
{{% /note %}}

{{< code-toggle file="config" >}}
[blackfriday]
  angledQuotes = true
  fractions = false
  plainIDAnchors = true
  extensions = ["hardLineBreak"]
{{< /code-toggle >}}

## Configure Additional Output Formats

Hugo v0.20 introduced the ability to render your content to multiple output formats (e.g., to JSON, AMP html, or CSV). See [Output Formats][] for information on how to add these values to your Hugo project's configuration file.

## 配置格式规范

* [TOML Spec](https://github.com/toml-lang/toml)
* [YAML Spec](http://yaml.org/spec/)
* [JSON Spec](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf)

[`.Site.Params`]: /variables/site/
[directory structure]: /getting-started/directory-structure
[Output Formats]: /templates/output-formats/