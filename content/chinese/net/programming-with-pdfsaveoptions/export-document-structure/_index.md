---
title: 将 Word 文档结构导出为 PDF 文档
linktitle: 将 Word 文档结构导出为 PDF 文档
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将 Word 文档结构导出为 PDF 文档的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/export-document-structure/
---

本文提供了有关如何使用 Aspose.Words for .NET 的“将 Word 文档结构导出为 PDF 文档”功能的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何导出文档的结构并生成具有可见文档结构的 PDF。

开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到该库和安装说明。

## 步骤1：定义文档目录

首先，您需要定义文档所在目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：上传文件

接下来，我们需要加载要处理的文档。在此示例中，我们假设文档名为“Paragraphs.docx”，位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## 步骤 3：配置保存为 PDF 选项

为了导出文档结构，并在编辑 PDF 文件时使该结构在 Adobe Acrobat Pro 的“内容”导航窗格中可见，我们需要配置`PdfSaveOptions`对象与`ExportDocumentStructure`属性设置为`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## 步骤 4：将文档保存为包含文档结构的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

就这样！您已成功导出文档结构并使用 Aspose.Words for .NET 生成了具有可见文档结构的 PDF。

### 使用 Aspose.Words for .NET 导出文档结构的示例源代码


```csharp

            //文档目录的路径。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            //文件大小将会增加，结构将在“内容”导航窗格中可见
            //Adobe Acrobat Pro，在编辑 .pdf 时。
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 将 Word 文档的结构导出为 PDF 文档。按照概述的步骤，您可以轻松生成文档结构可见的 PDF，从而更轻松地浏览和搜索文档。使用 Aspose.Words for .NET 的功能导出 Word 文档的结构并创建结构良好的 PDF。

### 经常问的问题

#### 问：什么是将 Word 文档的结构导出为 PDF 文档？
答：将 Word 文档的结构导出为 PDF 文档会创建具有可见文档结构的 PDF。文档结构通常包括标题、章节、段落和文档的其他结构化元素。此结构可用于在 PDF 文档中导航和搜索。

#### 问：如何使用 Aspose.Words for .NET 将 Word 文档的结构导出为 PDF 文档？
答：要使用 Aspose.Words for .NET 将 Word 文档的结构导出为 PDF 文档，请按照以下步骤操作：

创建一个实例`Document`指定 Word 文档路径的类。

创建一个实例`PdfSaveOptions`类并设置`ExportDocumentStructure`财产`true`。这将导出文档结构，并使其在编辑 PDF 文件时在 Adobe Acrobat Pro 的“内容”导航窗格中可见。

使用`Save`方法`Document`通过指定保存选项将文档保存为 PDF 格式。

#### 问：如何使用 Adobe Acrobat Pro 查看 PDF 文档的结构？
答：要使用 Adobe Acrobat Pro 查看 PDF 文档的结构，请按照以下步骤操作：

在 Adobe Acrobat Pro 中打开 PDF 文档。

在左侧导航栏中，单击“内容”图标，显示“内容”导航窗格。

在“内容”导航窗格中，您将看到包含标题、章节和其他结构化元素的文档结构。