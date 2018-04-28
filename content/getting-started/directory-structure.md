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
: Every Hugo project should have a configuration file in TOML, YAML, or JSON format at the root. Many sites may need little to no configuration, but Hugo ships with a large number of [configuration directives][] for more granular directions on how you want Hugo to build your website.

[`content`][]
: All content for your website will live inside this directory. Each top-level folder in Hugo is considered a [content section][]. For example, if your site has three main sections---`blog`, `articles`, and `tutorials`---you will have three directories at `content/blog`, `content/articles`, and `content/tutorials`. Hugo uses sections to assign default [content types][].

[`data`](/templates/data-templates/)
: This directory is used to store configuration files that can be
used by Hugo when generating your website. You can write these files in YAML, JSON, or TOML format. In addition to the files you add to this folder, you can also create [data templates][] that pull from dynamic content.

[`layouts`][]
: Stores templates in the form of `.html` files that specify how views of your content will be rendered into a static website. Templates include [list pages][lists], your [homepage][], [taxonomy templates][], [partials][], [single page templates][singles], and more.

[`static`][]
: Stores all the static content for your future website: images, CSS, JavaScript, etc. When Hugo builds your site, all assets inside your static directory are copied over as-is. A good example of using the `static` folder is for [verifying site ownership on Google Search Console][searchconsole], where you want Hugo to copy over a complete HTML file without modifying its content.

{{% note %}}
From **Hugo 0.31** you can have multiple static directories.
{{% /note %}}

{{% note %}}
Hugo does not currently ship with an asset pipeline ([#3207](https://github.com/gohugoio/hugo/issues/3207)). You can solicit support from the community in the [Hugo forums](https://discourse.gohugo.io) or check out a few of the [Hugo starter kits](/tools/starter-kits/) for examples of how Hugo developers are managing static assets.
{{% /note %}}

[configuration directives]: /getting-started/configuration/#all-variables-yaml
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
