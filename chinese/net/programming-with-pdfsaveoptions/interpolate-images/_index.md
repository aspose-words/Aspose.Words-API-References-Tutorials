---
title: 插值图像
linktitle: 插值图像
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 启用图像插值的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/interpolate-images/
---

本文提供了有关如何使用 Aspose.Words for .NET 的图像插值功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在转换为 PDF 时启用图像插值。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：上传文件

接下来，我们需要加载我们要处理的文档。在此示例中，我们假设文档名为“Rendering.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第 3 步：配置使用帧插值另存为 PDF 的选项

要在转换为 PDF 时启用图像插值，我们需要配置`PdfSaveOptions`通过设置对象`InterpolateImages`财产给`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };
```

## 第 4 步：将文档另存为带帧插值的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

就这样 ！在使用 Aspose.Words for .NET 将文档转换为 PDF 时，您已成功启用图像插值。

### 使用 Aspose.Words for .NET 进行图像插值的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);

```
