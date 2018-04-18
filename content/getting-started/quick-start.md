---
title: 快速入门
linktitle: 快速入门
description: 使用Ananke主题创建一个Hugo站点。
date: 2017-09-13
trabskate: 2018-07-17
weight: 10
sections_weight: 10
---

> 此快速入门示例运行在`macOS`平台上。有关如何在其他操作系统上安装Hugo，请参阅[安装](../installing)。
> 同时，你还需要安装[Git](https://git-scm.com/downloads)来运行本教程。

## 第一步：安装Hugo

> `Homebrew`是`macOS`平台下的软件包管理工具，你可以从[brew.sh](https://brew.sh/)安装。如果你使用Windows或其他操作系统，请参阅[安装](../installing)。

```bash
brew install hugo
```

执行以下命令检测你是否安装成功：

```bash
hugo version
```


## 第二步：创建站点

```bash
hugo new site quickstart
```

这个命令将把Hugo创建在`quickstart`文件夹中。

## 第二步：加载主题

访问[官方主题站（英文）](https://themes.gohugo.io/)来获取更多主题。此示例将使用[Ananke主题](https://themes.gohugo.io/gohugo-theme-ananke/)。

```bash
cd quickstart;\
git init;\
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke;\

# Edit your config.toml configuration file
# and add the Ananke theme.
echo 'theme = "ananke"' >> config.toml
```

## 第四步：添加文章

```
hugo new posts/my-first-post.md
```

现在你已经创建好了一篇文章，你可以选择在执行以下步骤前先编辑一下内容。完成后，在[草稿模式](../usage/)下运行Hugo：

```
▶ hugo server -D

Started building sites ...
Built site for language en:
1 of 1 draft rendered
0 future content
0 expired content
1 regular pages created
8 other pages created
0 non-page files copied
1 paginator pages created
0 categories created
0 tags created
total in 18 ms
Watching for changes in /Users/bep/sites/quickstart/{data,content,layouts,static,themes}
Serving pages from memory
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

**在浏览器中输入[http://localhost:1313/](http://localhost:1313/)打开这个Hugo站点。**

## 第五步：自定义主题

你的网站看起来不错，但在你上传并发布之前，有一些配置需要调整一下。

### 网站配置

在文本编辑器中打开根目录的`config.toml`文件：

```
baseURL = "https://example.org/"
languageCode = "en-us"
title = "My New Hugo Site"
theme = "ananke"
```

把`title`中的内容替换成你自己的标题。另外，如果你已经有一个域名，把他填写在`baseURL`中。注意，在本地开发时不需要修改此参数。

> **提示：**在Hugo运行时，对站点配置或文件内容的修改都会实时反应在浏览器中。

有关此主题（Ananke）的配置选项，请参阅[Ananke主题](https://github.com/budparr/gohugo-theme-ananke)。

**有关Hugo主题的配置选项，请参阅[自定义主题](../../themes/customizing/)。**

## 概览

本页面视频请参见[原文](https://gohugo.io/getting-started/quick-start/)。