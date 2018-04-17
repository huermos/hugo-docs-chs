---
title: 版本更新
linktitle: Hugo v0.32 版本更新说明
description: 关于页面组织，图像处理等。
date: 2018-04-02
translate: 2018-04-16
weight: 2
sections_weight: 2
---

> 本页面内容为0.32版本更新内容，将在日后移动到其相应的页面。临时置于此处供快速参考和调试。

另请参阅[bep](https://github.com/bep/)的这个demo，他提供了这些新功能：

* http://hugotest.bep.is
* https://github.com/bep/hugotest

## 页面组织

### 组织你的内容

![img](https://d33wubrfki0l68.cloudfront.net/4c06428897df426b60d300c8f6de175b37d7fdde/637cb/images/hugo-content-bundles.png)

上面的content文件夹包含内容页面（`md`如Markdown）与图像资源。

> Hugo允许你使用任何符合MIME的文件类型（如`json`就被完美支持）。如果你想要与众不同，Hugo也允许你定义你自己的[媒体类型](/templates/output-formats/#media-types)。

上图中的三个红框分别表示以下三项内容：

1. 带有一张图片的首页（`1-logo.png`）
2. 带有两张图片和两篇文章（`content1.md`，`content2.md`）的博客页。注意`_index.md`是本章节的URL。
3. 带有内附两张图片的文件夹和一个内容（`cats-info.md`）的文章（`hugo-is-cool`）。注意`index.md`是此文章的URL。

而红框外的`blog/posts`是常规的独立页面。

> 注意，如果hugo运行在watch（aka服务或实时预览模式）或`--navigateToChanged`下，修改`content`文件夹内任何文件都会重新加载预览页面。

#### 排序

* 所有页面默认按照标准Hugo排序规则进行排序
* 图片和其他文件按首字母排序

### 处理模板中的页面资源

#### 列出所有资源

```go-html-template
{{ range .Resources }}
<li><a href="{{ .RelPermalink }}">{{ .ResourceType | title }}</a></li>
{{ end }}
```

对于绝对URL，请使用`.Permalink`。

**注意：**固定连接（permalink）与内容页面有关，谨慎设置固定连接的参数。此外，被包含的页面资源将不具有`RelPermalink`值。

#### 按类型列出所有资源

```go-html-template
{{ with .Resources.ByType "image" }}
{{ end }}
```

如果在此处使用`page`将表示网页（pages）。除此之外，你可以使用MIME中的其他类型，包括`image`和`json`等。

#### 获取特定资源

```go-html-template
{{ $logo := .Resources.GetByPrefix "logo" }}
{{ with $logo }}
{{ end }}
```

#### 包含页面资源内容

```go-html-template
{{ with .Resources.ByType "page" }}
{{ range . }}
<h3>{{ .Title }}</h3>
{{ .Content }}
{{ end }}
{{ end }}
```

## 图像处理

`image`资源具有三种处理方法：`Resize`，`Fit`和`Fill`:

##### 调整大小（`Resize`）

将图片调整为指定尺寸。使用`{{ $logo.Resize "200x" }}`将图片宽度改为200px，比例不变。使用`{{ $logo.Resize "200x100" }}`会同时修改图片的宽度和高度。

##### 适合（`Fit`）

缩放图片至指定尺寸。使用`{{ $logo.Fit "200x100" }}`将图片放在200px x 100px的容器中。

##### 填充（`Fill`）

调整并裁剪图片至指定尺寸。使用`{{ $logo.Fill "200x100" }}`将调整图片尺寸并裁剪为200px x 100px。

> Hugo的图像处理**不会保留EXIF元数据**，因为目前Go的[图像处理模块](https://github.com/golang/go/search?q=exif&type=Issues&utf8=%E2%9C%93)暂不支持。此功能预计在未来添加支持。

### 示例

对应图片请参见[原文](https://gohugo.io/about/new-in-032/)

```go-html-template
{{ $original := .Page.Resources.GetMatch (printf "%s*" (.Get 0)) }}
{{ $command := .Get 1 }}
{{ $options := .Get 2 }}
{{ if eq $command "Fit"}}
{{ .Scratch.Set "image" ($original.Fit $options) }}
{{ else if eq $command "Resize"}}
{{ .Scratch.Set "image" ($original.Resize $options) }}
{{ else if eq $command "Fill"}}
{{ .Scratch.Set "image" ($original.Fill $options) }}
{{ else }}
{{ errorf "Invalid image processing command: Must be one of Fit, Fill or Resize."}}
{{ end }}
{{ $image := .Scratch.Get "image" }}
<figure style="width: {{ add $image.Width 3 }}px; padding: 3px; background-color: #cccc">
	<img src="{{ $image.RelPermalink }}" width="{{ $image.Width }}" height="{{ $image.Height }}">
	<figcaption>
	<small>
	{{ with .Inner }}
	{{ . }}
	{{ else }}
	.{{ $command }} "{{ $options }}"
	{{ end }}
	</small>
	</figcaption>
</figure> 
```

这样使用：

```go-html-template
{{</* imgproc sunset Resize "300x" */>}}
```

### 图像处理选项

除了调节尺寸以外，Hugo还支持一些额外的图像处理选项：

##### 起始位置（Anchor）

仅在`Fill`下生效。当你需要粗略定位图片的位置时，这项功能十分有用。可选值为：`Center`, `TopLeft`, `Top`, `TopRight`, `Left`, `Right`, `BottomLeft`, `Bottom`, `BottomRight`。例如：`{{ $logo.Fill "200x100 BottomLeft" }}`。

##### JPEG质量（JPEG Quality）

仅与JPEG图像有关。可选值从1至100，值越高质量越高。默认值为75。例如：`{{ $logo.Resize "200x q50" }}`

##### 旋转（Rotate）

逆时针旋转图像至给定值（角度）。旋转会首先执行以确保尺寸正确，目的是为了手动纠正JPEG的[EXIF方向](https://github.com/golang/go/issues/4341)。例如：`{{ $logo.Resize "200x r90" }}`。

##### 重新采样过滤器

过滤器用于调整尺寸。默认是`Box`，一个用于缩小图像的，简单快速的重采样过滤器。参阅 https://github.com/disintegration/imaging 获取更多信息。如果你希望更快的处理trade质量，可以测试此选项。

### 性能

处理后的图像被储存在`<project-dir>/resources`下，此位置可在`resourceDir`配置中设置。此文件夹有意被放置在项目中，因为我们建议将这些文件夹作为项目的一部分加入到源代码控制中。这些图像并不是由Hugo快速生成的。不过一旦生成，它们便可以被重复使用。

如果你修改了图片的配置（如尺寸），删除或重命名图像等，这些未被使用的图像将会占用相应空间。

执行以下命令清除这些文件：

```bash
hugo --gc
```

> **GC**是垃圾回收（Garbage Collectio）的缩写。

## 配置

### 默认的图像处理配置

你可以在`config.toml`中新建一个`imaging`段来自定义图像处理选项：

```toml
[imaging]
# Default resample filter used for resizing. Default is Box,
# a simple and fast averaging filter appropriate for downscaling.
# See https://github.com/disintegration/imaging
resampleFilter = "box"

# Defatult JPEG quality setting. Default is 75.
quality = 68
```