---
title: 设置大纲选项
linktitle: 设置大纲选项
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在 PDF 文档中设置大纲选项的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/set-outline-options/
---

本文提供了有关如何使用 Aspose.Words for .NET 将大纲选项设置为图元文件大小功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在文档中设置大纲选项并生成具有相应大纲选项的 PDF。

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

## 第 3 步：使用计划选项配置另存为 PDF 选项

要在生成的 PDF 中设置大纲选项，我们需要配置`PdfSaveOptions`目的。我们可以设置标题大纲级别的数量（`HeadingsOutlineLevels`) 和扩展大纲级别的数量 (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## 第 4 步：使用大纲选项将文档另存为 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

就这样 ！您已经成功地在文档中设置了大纲选项，并使用 Aspose.Words for .NET 生成了具有相应大纲选项的 PDF。

### 使用 Aspose.Words for .NET 将计划选项设置为元文件大小的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```
