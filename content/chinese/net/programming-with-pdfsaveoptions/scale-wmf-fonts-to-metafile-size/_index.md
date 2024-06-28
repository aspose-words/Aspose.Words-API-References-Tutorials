---
title: 通过将 Wmf 字体缩放到图元文件大小来减小 PDF 大小
linktitle: 通过将 Wmf 字体缩放到图元文件大小来减小 PDF 大小
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 转换为 PDF 时，通过将 wmf 字体缩放为图元文件大小来减小 pdf 大小的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

本文提供了有关如何使用 Aspose.Words for .NET 将 wmf 字体缩放到图元文件大小功能来减小 pdf 大小的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在转换为 PDF 时启用或禁用 WMF 字体缩放。

在开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第1步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上传文件

接下来，我们需要加载我们想要处理的文档。在此示例中，我们假设文档名为“WMF with text.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 步骤 3：配置图元文件渲染选项

要启用或禁用 WMF 字体缩放到图元文件大小，我们需要配置`MetafileRenderingOptions`目的。在此示例中，我们通过设置禁用字体缩放`ScaleWmfFontsToMetafileSize`财产给`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 步骤 4：使用图元文件渲染选项配置另存为 PDF 选项

最后，我们可以使用之前配置的图元文件渲染选项来配置“保存为 PDF”选项。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## 步骤 5：使用图元文件渲染选项将文档另存为 PDF

使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

就这样 ！您已在转换时成功启用或禁用 WMF 字体缩放到图元文件大小

使用 Aspose.Words for .NET 的 PDF 文档。

### 使用 Aspose.Words for .NET 将 WMF 字体缩放为图元文件大小的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//如果 Aspose.Words 无法正确将某些图元文件记录渲染为矢量图形
	//然后Aspose.Words 将此图元文件呈现为位图。
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 在 PDF 文档中启用或禁用将 WMF 字体大小调整为图元文件大小。通过执行所述步骤，您可以轻松控制在转换为 PDF 文档时是否应调整 WMF 字体大小以匹配图元文件大小。这可以帮助您减小生成的 PDF 文件的大小并提高渲染性能。请务必指定文档的正确路径并根据需要配置图元文件渲染选项。

### 经常问的问题

#### 问：什么是在 PDF 文档中将 WMF 字体大小调整为图元文件大小？
答：将 WMF 字体大小调整为 PDF 文档中的图元文件大小是一项功能，用于控制在转换为 PDF 文档时是否应缩放 WMF 字体以匹配图元文件大小。启用此功能后，WMF 字体将缩放以匹配图元文件的大小，这可能会减小生成的 PDF 文档的大小。

#### 问：如何使用 Aspose.Words for .NET 启用或禁用将 PDF 文档中的 WMF 字体大小调整为图元文件大小？
答：要使用 Aspose.Words for .NET 在 PDF 文档中启用或禁用将 WMF 字体大小调整为图元文件大小，请按照以下步骤操作：

通过替换设置文档所在的目录路径`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

使用以下命令加载要处理的文档`Document`类并指定指定文档目录中Word文档的路径。

通过创建图元文件的实例来配置图元文件渲染选项`MetafileRenderingOptions`类并设置`ScaleWmfFontsToMetafileSize`财产给`true`启用 WMF 字体缩放至图元文件大小，或`false`禁用此功能。

通过创建一个实例来配置另存为 PDF 选项`PdfSaveOptions`类并使用之前配置的图元文件渲染选项。

使用以下命令将文档保存为 PDF 格式`Save`的方法`Document`类指定路径和保存选项。

#### 问：在 PDF 文档中将 WMF 字体大小调整为图元文件大小有什么好处？
答：在 PDF 文档中将 WMF 字体大小调整为图元文件大小的优点是：

PDF 文件大小减小：将 WMF 字体大小调整为图元文件大小可以通过使字体大小适应图元文件需求来减小生成的 PDF 文档的大小。

改进的性能：通过将 WMF 字体的大小调整为图元文件的尺寸，PDF 文档的渲染可以更快、更高效。