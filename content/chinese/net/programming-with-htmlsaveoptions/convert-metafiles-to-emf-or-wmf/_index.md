---
title: 将图元文件转换为 Emf 或 Wmf
linktitle: 将图元文件转换为 Emf 或 Wmf
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将文档转换为 HTML 时，将元文件转换为 EMF 或 WMF 格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

在本教程中，我们将引导您使用 Aspose.Words for .NET 将元文件转换为 EMF 或 WMF 格式的 C# 源代码。此功能允许您在将文档转换为 HTML 时将元文件格式的图像转换为更兼容的格式，例如 EMF 或 WMF。

## 步骤 1：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：将图像插入文档

在此步骤中，我们将图像插入要转换的文档中。使用以下代码使用 HTML 标记从数据源插入图像：

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

此代码创建`Document`和`DocumentBuilder`构建文档。它插入一个`<img>`使用 base64 编码的图像将标签粘贴到文档中。

## 步骤 3：设置 HTML 保存选项

现在我们将设置 HTML 保存选项，包括用于图像的元文件格式。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

此代码创建`HtmlSaveOptions`并设置`MetafileFormat`到`HtmlMetafileFormat.EmfOrWmf`指定在转换为 HTML 时应将元文件转换为 EMF 或 WMF 格式。

## 步骤 4：将文档转换并保存为 HTML

最后，我们将使用之前定义的保存 HTML 选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

此代码将文档转换为 HTML，并根据设置的保存选项，将其保存为包含转换后的 EMF 或 WMF 格式的图元文件的文件。

### 使用 Aspose.Words for .NET 将元文件转换为 Emf 或 Wmf 的示例源代码

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

确保在`dataDir`多变的。

现在，您已经了解了如何在使用 Aspose.Words for .NET 将文档转换为 HTML 时将元文件转换为 EMF 或 WMF 格式。通过遵循本教程中提供的分步指南，您可以轻松管理转换后的 HTML 文档中的元文件。