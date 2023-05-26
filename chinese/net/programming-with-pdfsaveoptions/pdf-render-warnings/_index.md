---
title: PDF 渲染警告
linktitle: PDF 渲染警告
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 处理 PDF 呈现警告的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

本文提供了有关如何将 PDF 呈现警告功能与 Aspose.Words for .NET 一起使用的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解在转换为 PDF 时如何处理渲染警告。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：上传文件

接下来，我们需要加载我们要处理的文档。在此示例中，我们假设文档名为“WMF with image.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## 第 3 步：配置带有呈现警告的另存为 PDF 选项

要在转换为 PDF 时处理渲染警告，我们需要配置`MetafileRenderingOptions`对象来指定图元文件的呈现方式。我们还使用`HandleDocumentWarnings`选项来处理保存文档时生成的警告。

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## 第 4 步：将文档另存为带有呈现警告的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## 第 5 步：处理渲染警告

可以使用自定义警告处理程序检索保存文档时生成的渲染警告。在这个例子中，我们只是打印每个警告的描述。

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

就这样 ！您已成功处理转换文档时的渲染警告

  使用 Aspose.Words for .NET 转换为 PDF。

### 使用 Aspose.Words for .NET 的 PDF 呈现警告示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	//如果 Aspose.Words 无法正确呈现某些图元文件记录
	//转换为矢量图形，然后 Aspose.Words 将此图元文件渲染为位图。
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	//当文件保存成功时，保存过程中出现的渲染警告被收集在这里。
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```
