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

与模板的[查找顺序](/templates/lookup-order/)类似，Hugo也有一个默认的规则去查找

Configuration Lookup Order

Similar to the template [lookup order][], Hugo has a default set of rules for searching for a configuration file in the root of your website's source directory as a default behavior:

1. `./config.toml`
2. `./config.yaml`
3. `./config.json`

在你的`config`文件中，你可以

In your `config` file, you can direct Hugo as to how you want your website rendered, control your website's menus, and arbitrarily define site-wide parameters specific to your project.


## 示例配置

The following is a typical example of a configuration file. The values nested under `params:` will populate the [`.Site.Params`][] variable for use in [templates][]:

{{< code-toggle file="config">}}
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
{{< /code-toggle >}}

## Configure with Environment Variables

In addition to the 3 config options already mentioned, configuration key-values can be defined through operating system environment variables.

For example, the following command will effectively set a website's title on Unix-like systems:

```
$ env HUGO_TITLE="Some Title" hugo
```

This is really useful if you use a service such as Netlify to deploy your site. Look at the Hugo docs [Netlify configuration file](https://github.com/gohugoio/hugoDocs/blob/master/netlify.toml) for an example.

{{% note "Setting Environment Variables" %}}
Names must be prefixed with `HUGO_` and the configuration key must be set in uppercase when setting operating system environment variables.
{{% /note %}}

{{< todo >}}
Test and document setting params via JSON env var.
{{< /todo >}}

## Ignore Files When Rendering

The following statement inside `./config.toml` will cause Hugo to ignore files ending with `.foo` and `.boo` when rendering:

```
ignoreFiles = [ "\\.foo$", "\\.boo$" ]
```

The above is a list of regular expressions. Note that the backslash (`\`) character is escaped in this example to keep TOML happy.

## 配置头文件

### Configure Dates

Dates are important in Hugo, and you can configure how Hugo assigns dates to your content pages. You do this by adding a `frontmatter` section to your `config.toml`.


The default configuration is:

```toml
[frontmatter]
date = ["date","publishDate", "lastmod"]
lastmod = [":git" "lastmod", "date","publishDate"]
publishDate = ["publishDate", "date"]
expiryDate = ["expiryDate"]
```

If you, as an example, have a non-standard date parameter in some of your content, you can override the setting for `date`:

 ```toml
[frontmatter]
date = [ "myDate", ":default"]
 ```

The `:default` is a shortcut to the default settings. The above will set `.Date` to the date value in `myDate` if present, if not we will look in `date`,`publishDate`, `lastmod` and pick the first valid date.

In the list to the right, values starting with ":" are date handlers with a special meaning (see below). The others are just names of date parameters (case insensitive) in your front matter configuration.  Also note that Hugo have some built-in aliases to the above: `lastmod` => `modified`, `publishDate` => `pubdate`, `published` and `expiryDate` => `unpublishdate`. With that, as an example, using `pubDate` as a date in front matter, will, by default, be assigned to `.PublishDate`.

The special date handlers are:


`:fileModTime`
: Fetches the date from the content file's last modification timestamp.

An example:

 ```toml
[frontmatter]
lastmod = ["lastmod" ,":fileModTime", ":default"]
 ```


The above will try first to extract the value for `.Lastmod` starting with the `lastmod` front matter parameter, then the content file's modification timestamp. The last, `:default` should not be needed here, but Hugo will finally look for a valid date in `:git`, `date` and then `publishDate`.


`:filename`
: Fetches the date from the content file's filename. For example, `218-02-22-mypage.md` will extract the date `218-02-22`. Also, if `slug is not set, `mypage` will be used as the value for `.Slug`.

An example:

```toml
[frontmatter]
date  = [":filename", ":default"]
```

The above will try first to extract the value for `.Date` from the filename, then it will look in front matter parameters `date`, `publishDate` and lastly `lastmod`.


`:git`
: This is the Git author date for the last revision of this content file. This will only be set if `--enableGitInfo` is set or `enableGitInfo = true` is set in site config.

## 配置Blackfriday

[Blackfriday](https://github.com/russross/blackfriday) is Hugo's built-in Markdown rendering engine.

Hugo typically configures Blackfriday with sane default values that should fit most use cases reasonably well.

However, if you have specific needs with respect to Markdown, Hugo exposes some of its Blackfriday behavior options for you to alter. The following table lists these Hugo options, paired with the corresponding flags from Blackfriday's source code ( [html.go](https://github.com/russross/blackfriday/blob/master/html.go) and [markdown.go](https://github.com/russross/blackfriday/blob/master/markdown.go)).

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

## Configuration Format Specs

* [TOML Spec][toml]
* [YAML Spec][yaml]
* [JSON Spec][json]

[`.Site.Params`]: /variables/site/
[directory structure]: /getting-started/directory-structure
[json]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf "Specification for JSON, JavaScript Object Notation"
[lookup order]: 
[Output Formats]: /templates/output-formats/
[templates]: /templates/
[toml]: https://github.com/toml-lang/toml
[yaml]: http://yaml.org/spec/
