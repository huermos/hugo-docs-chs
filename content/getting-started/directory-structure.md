---
title: 目录结构
linktitle: 目录结构
description: Hugo使用CLI创建了一个目录结构。通过编译这个目录来生成一个完整的网站。
date: 2018-02-27
translate: 2018-04-24
lastmod: 2018-04-24
translator: huermos
weight: 50
---

## 新的网站脚手架

{{< youtube sB0HLHjgQ7E >}}

在命令行中运行`hugo new site`将会创建一个包含以下元素的目录结构：

```
.
├── archetypes
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes
```

## 目录结构解释

以下是Hugo文档中每个最高级目录的概览，点击目录名即可转向其详细介绍链接。

[`archetypes`](/content-management/archetypes/)
: 你可以使用`hugo new`来创建一个新的内容文件。默认情况下，这个内容文件的头文件中至少包含`date`，`title`和`draft = true`三个项目。这将节省你的时间并保持内容文件配置的一致性。当然，你可以在[archetypes](/content-management/archetypes/)里自定义你自己的头文件预配置。

[`config.toml`](/getting-started/configuration/)
: 每一个Hugo项目的根目录下都有一个用TOML，YAML或JSON写成的配置文件。尽管一些网站项目不需要这个配置文件，或者只需要其中的一小部分，但Hugo依然提供了大量的[配置参数](/getting-started/configuration/#配置参数)来帮助你构建你的网站。

[`content`](/content-management/organization/)
: 你的所有内容文件都位于这个目录中。其中的每个一级目录都被视作Hugo的[内容部分](/content-management/sections/)。例如，如果你的网站包含三个部分：`blog`，`articles`和`tutorials`，那么你就需要拥有`content/blog`，`content/articles`和`content/tutorials`这三个目录。他们都遵循默认的[内容类型](/content-management/types/)。

[`data`](/templates/data-templates/)
: 此目录用来储存再生成网站时的配置文件。你可以使用TOML，YAML或JSON来编辑它们。除了你般存在这个文件夹中的文件意外，你也可以创建从动态内容中拉取的[数据模板](/templates/data-templates/)。

[`layouts`](/templates/)
: 此目录用来储存`.html`格式的模板，它们用来定义网站渲染后的外观。模板包括你的[主页](/templates/homepage/)，[列表页面](/templates/list/)，[分类模板](templates/taxonomy-templates/)，[局部模板](/templates/partials/)和[单页模板](/templates/single-page-templates/)等等。

[`static`][]
: Stores all the static content for your future website: images, CSS, JavaScript, etc. When Hugo builds your site, all assets inside your static directory are copied over as-is. A good example of using the `static` folder is for [verifying site ownership on Google Search Console][searchconsole], where you want Hugo to copy over a complete HTML file without modifying its content.

```
从**Hugo 0.31**开始你可以拥有多个静态（static）目录。
```

{{% note %}}
Hugo does not currently ship with an asset pipeline ([#3207](https://github.com/gohugoio/hugo/issues/3207)). You can solicit support from the community in the [Hugo forums](https://discourse.gohugo.io) or check out a few of the [Hugo starter kits](/tools/starter-kits/) for examples of how Hugo developers are managing static assets.
{{% /note %}}

[`content`]: /content-management/organization/
[content section]: /content-management/sections/
[content types]: /content-management/types/
[data templates]: /templates/data-templates/
[homepage]: /templates/homepage/
[`layouts`]: /templates/
[`static`]: /content-management/static-files/
[lists]: /templates/list/
[pagevars]: /variables/page/
[partials]: /templates/partials/
[searchconsole]: https://support.google.com/analytics/answer/1142414?hl=en
[singles]: /templates/single-page-templates/
[starters]: /tools/starter-kits/
[taxonomies]: /content-management/taxonomies/
[taxonomy templates]: /templates/taxonomy-templates/
[types]: /content-management/types/
