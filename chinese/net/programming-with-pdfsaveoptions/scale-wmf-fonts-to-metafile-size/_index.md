---
title: 将 Wmf 字体缩放到图元文件大小
linktitle: 将 Wmf 字体缩放到图元文件大小
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 转换为 PDF 时调整 WMF 字体大小的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

本文提供了有关如何将 WMF 字体缩放到图元文件大小功能与 Aspose.Words for .NET 一起使用的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在转换为 PDF 时启用或禁用 WMF 字体缩放。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：上传文件

接下来，我们需要加载我们要处理的文档。在此示例中，我们假设文档名为“WMF with text.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 第 3 步：配置图元文件呈现选项

要启用或禁用 WMF 字体缩放到图元文件大小，我们需要配置`MetafileRenderingOptions`目的。在此示例中，我们通过设置`ScaleWmfFontsToMetafileSize`财产给`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 第 4 步：使用图元文件呈现选项配置另存为 PDF 选项

最后，我们可以使用之前配置的图元文件呈现选项来配置保存为 PDF 的选项。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## 第 5 步：使用图元文件呈现选项将文档另存为 PDF

使用先前配置的保存选项以 PDF 格式保存文档。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

就这样 ！您已在转换时成功启用或禁用 WMF 字体缩放到图元文件大小

使用 Aspose.Words for .NET 的 PDF 文档。

### 使用 Aspose.Words for .NET 将 WMF 字体缩放到元文件大小的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//如果 Aspose.Words 无法正确地将某些图元文件记录呈现为矢量图形
	//然后 Aspose.Words 将这个图元文件呈现为位图。
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```
