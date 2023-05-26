---
title: 出口文件结构
linktitle: 出口文件结构
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 导出文档结构的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/export-document-structure/
---

本文提供了有关如何使用 Aspose.Words for .NET 的导出文档结构功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何导出文档结构并生成文档结构可见的 PDF。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：上传文件

接下来，我们需要加载我们要处理的文档。在此示例中，我们假设文档名为“Paragraphs.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## 第 3 步：配置另存为 PDF 选项

要在编辑 PDF 文件时导出文档结构并使结构在 Adobe Acrobat Pro 的“内容”导航窗格中可见，我们需要配置`PdfSaveOptions`对象与`ExportDocumentStructure`属性设置为`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## 步骤 4：将文档另存为具有文档结构的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

就这样 ！您已经使用 Aspose.Words for .NET 成功导出了文档结构并生成了文档结构可见的 PDF。

### 使用 Aspose.Words for .NET 导出文档结构的示例源代码


```csharp

            //文档目录的路径。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            //文件大小将增加，结构将在“内容”导航窗格中可见
            //Adobe Acrobat Pro，同时编辑 .pdf。
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```
