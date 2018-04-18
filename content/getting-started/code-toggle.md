---
title: 代码切换器
linktitle: 代码切换器
description: 测试并演示代码切换器的效果。
date: 2018-04-02
translate: 2018-04-17
weight: 60
sections_weight: 60
---

## 设置代码切换器

以下是一个使用了代码切换器的简码例子。其目的是让用户通过点击不同的选项卡来选择对应的语言。这样一来，此页面上的每个代码切换器中的内容都会被被切换到指定语言。同时，这个语言也会被储存在用户的`localStorage`中，即使用户访问其他页面时，代码切换器也会显示最后选用的语言。

> **译者注：**`Hugo中文化官方文档`没用启用代码切换器，因此所有使用了此配置的展示将不起作用。

## 一个代码切换器

```
baseURL = "https://yoursite.example.com/"
footnoteReturnLinkContents = "↩"
title = "My Hugo Site"

[params]
  AuthorName = "Jon Doe"
  GitHubUser = "spf13"
  ListOfFoo = ["foo1", "foo2"]
  SidebarRecentLimit = 5
  Subtitle = "Hugo is Absurdly Fast!"

[permalinks]
  post = "/:year/:month/:title/"
```

## 另一个代码切换器

```
description = ""
features = ["", ""]
homepage = "https://github.com/budparr/gohugo.io"
license = "MIT"
licenselink = "https://github.com/budparr/gohugo.io/blob/master/LICENSE.md"
min_version = 0.18
name = "Hugo Theme"
tags = ["website"]

[author]
  homepage = "https://github.com/budparr"
  name = "Bud Parr"
```

## 两个普通的代码块

bf-config.toml

```
[blackfriday]
  angledQuotes = true
  fractions = false
  plainIDAnchors = true
  extensions = ["hardLineBreak"]
```

bf-config.yml

```
blackfriday:
  angledQuotes: true
  fractions: false
  plainIDAnchors: true
  extensions:
    - hardLineBreak
```