---
title: 将 Word 文档页眉页脚书签导出到 PDF 文档
linktitle: 将 Word 文档页眉页脚书签导出到 PDF 文档
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将 Word 文档页眉页脚书签导出到 pdf 文档书签的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

本文提供了有关如何使用 Aspose.Words for .NET 将 Word 文档页眉页脚书签导出到 pdf 文档功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何从文档的页眉和页脚导出书签并生成带有适当书签的 PDF。

在开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第1步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上传文件

接下来，我们需要加载我们想要处理的文档。在此示例中，我们假设文档名为“Bookmarks in headers and footers.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## 步骤 3：配置另存为 PDF 选项

要导出页眉和页脚书签，我们需要配置`PdfSaveOptions`目的。在此示例中，我们将默认书签大纲级别设置为 1，并将页眉和页脚书签导出模式设置为“第一”。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## 步骤 4：将文档另存为带有页眉和页脚书签的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

就这样 ！您已成功从文档中导出页眉和页脚书签，并使用 Aspose.Words for .NET 生成了带有适当书签的 PDF。

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

## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 将页眉和页脚书签从 Word 文档导出到 PDF 文档。导出的书签可以轻松导航并快速引用生成的 PDF 文档中相应的页眉和页脚。按照描述的步骤从文档导出页眉和页脚书签，并使用 Aspose.Words for .NET 生成带有适当书签的 PDF。请务必指定文档的正确路径并根据需要配置保存选项。

### 经常问的问题

### 问：什么是将页眉和页脚书签从 Word 文档导出到 PDF 文档？
答：将Word文档中的页眉和页脚书签导出到PDF文档是一项功能，可以从页眉和页脚中保留并生成PDF文档中的书签。原始 Word 文档的页脚。这使得用户可以使用与页眉和页脚相对应的书签快速轻松地浏览 PDF 文档。

### 问：如何使用 Aspose.Words for .NET 将页眉和页脚书签从 Word 文档导出到 PDF 文档？
答：要使用 Aspose.Words for .NET 将页眉和页脚书签从 Word 文档导出到 PDF 文档，请按照下列步骤操作：

通过替换设置文档所在的目录路径`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

使用以下命令加载要处理的文档`Document`类并指定指定文档目录中Word文档的路径。

通过创建一个实例来配置另存为 PDF 选项`PdfSaveOptions`类并设置适当的页眉和页脚书签选项。

使用以下命令将文档保存为 PDF 格式`Save`的方法`Document`指定路径和保存选项的类。

### 问：将页眉和页脚书签导出到 PDF 文档有什么好处？
答：将页眉和页脚书签导出到 PDF 文档的优点是：

轻松导航：书签允许用户通过引用特定的页眉和页脚轻松导航 PDF 文档。

快速参考：书签允许用户根据页眉和页脚快速找到 PDF 文档的相关部分。