---
title: 将图元文件转换为 Emf 或 Wmf
linktitle: 将图元文件转换为 Emf 或 Wmf
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将文档转换为 HTML 时将图元文件转换为 EMF 或 WMF 格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 将图元文件转换为 EMF 或 WMF 格式。此功能允许您在将文档转换为 HTML 时将图元文件格式的图像转换为更兼容的格式，例如 EMF 或 WMF。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：将图像插入文档

在此步骤中，我们将在要转换的文档中插入图像。使用以下代码通过 HTML 标记插入来自数据源的图像：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

这段代码创建了一个实例`Document`和`DocumentBuilder`构建文档。它插入一个`<img>`使用 base64 编码图像标记到文档中。

## 第 3 步：设置 HTML 保存选项

现在我们将设置 HTML 保存选项，包括用于图像的图元文件格式。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

这段代码创建了一个实例`HtmlSaveOptions`和集`MetafileFormat`到`HtmlMetafileFormat.EmfOrWmf`指定图元文件在转换为 HTML 时应转换为 EMF 或 WMF 格式。

## 步骤 4：将文档转换并保存为 HTML

最后，我们将使用之前定义的保存 HTML 选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

此代码将文档转换为 HTML，并将其保存到具有 EMF 或 WMF 格式的转换图元文件的文件中，具体取决于保存选项集。

### 使用 Aspose.Words for .NET 将图元文件转换为 Emf 或 Wmf 的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

请务必在文件目录中指定正确的路径`dataDir`多变的。

您现在已经了解了在使用 Aspose.Words for .NET 将文档转换为 HTML 时如何将图元文件转换为 EMF 或 WMF 格式。通过遵循本教程中提供的分步指南，您可以轻松管理转换后的 HTML 文档中的图元文件。