---
title: 导出页眉页脚书签
linktitle: 导出页眉页脚书签
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 导出页眉和页脚书签的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

本文提供了有关如何使用 Aspose.Words for .NET 的导出页眉和页脚书签功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何从文档的页眉和页脚导出书签并生成带有适当书签的 PDF。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：上传文件

接下来，我们需要加载我们要处理的文档。在此示例中，我们假设文档名为“Bookmarks in headers and footers.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## 第 3 步：配置另存为 PDF 选项

要导出页眉和页脚书签，我们需要配置`PdfSaveOptions`目的。在此示例中，我们将默认书签大纲级别设置为 1，并将页眉和页脚书签导出模式设置为“First”。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## 第 4 步：将文档另存为带有页眉和页脚书签的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

就这样 ！您已经成功地从文档中导出了页眉和页脚书签，并使用 Aspose.Words for .NET 生成了带有适当书签的 PDF。

### 使用 Aspose.Words for .NET 导出页眉和页脚书签的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```
