---
title: 将图元文件转换为 Svg
linktitle: 将图元文件转换为 Svg
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 将文档转换为 HTML 时将图元文件转换为 SVG 格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 将图元文件转换为 SVG 格式。此功能允许您在将文档转换为 HTML 时将图元文件转换为 SVG 格式。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：将 SVG 图像插入文档中

在此步骤中，我们将在要转换的文档中插入 SVG 图像。使用以下代码通过 HTML 标签插入 SVG 图像：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

这段代码创建了一个实例`Document`和`DocumentBuilder`构建文档。它插入一个`<svg>`标签包含一个`<polygon>`具有定义 SVG 图像的形状和样式的属性的元素。

## 第 3 步：设置 HTML 保存选项

现在我们将设置 HTML 保存选项，指定图元文件应转换为 SVG 格式。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

这段代码创建了一个实例`HtmlSaveOptions`和集`MetafileFormat`到`HtmlMetafileFormat.Svg`指定图元文件在转换为 HTML 时应转换为 SVG 格式。

## 步骤 4：将文档转换并保存为 HTML

最后，我们将使用之前定义的 HTML 保存选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

此代码将文档转换为 HTML，并将其保存到一个文件中，其中图元文件已转换为 SVG。

### 使用 Aspose.Words for .NET 将图元文件转换为 Svg 的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
