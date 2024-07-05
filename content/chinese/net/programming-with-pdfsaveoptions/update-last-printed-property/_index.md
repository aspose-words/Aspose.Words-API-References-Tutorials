---
title: 更新 PDF 文档中的上次打印属性
linktitle: 更新 PDF 文档中的上次打印属性
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 转换为 PDF 时更新“上次打印”属性的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

本文提供了有关如何使用 Aspose.Words for .NET 的 PDF 文档更新功能中的“上次打印”属性的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何配置在转换为 PDF 时更新“上次打印”属性的选项。

开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到该库和安装说明。

## 步骤1：定义文档目录

首先，您需要定义文档所在目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：上传文件

接下来，我们需要加载要处理的文档。在此示例中，我们假设文档名为“Rendering.docx”，位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：配置保存为 PDF 选项并更新“上次打印”属性

为了在转换为 PDF 时启用更新“上次打印”属性，我们需要配置`PdfSaveOptions`对象并设置`UpdateLastPrintedProperty`财产`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## 步骤 4：将文档保存为 PDF，并更新“上次打印”属性

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

就这样！您已成功启用使用 Aspose.Words for .NET 将文档转换为 PDF 时更新“上次打印”属性。

### 使用 Aspose.Words for .NET 更新“上次打印”属性的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 更新 PDF 文档中的“上次打印”属性。按照给定的步骤，您可以轻松配置在将文档转换为 PDF 时更新“上次打印”属性的选项。使用此功能可以跟踪文档使用情况和相关信息。

### 经常问的问题

#### 问：PDF 文档中的“上次打印”属性是什么？
答：PDF 文档中的“上次打印”属性是指文档上次打印的日期和时间。此属性可用于跟踪有关文档使用和管理的信息。

#### 问：如何使用 Aspose.Words for .NET 更新 PDF 文档中的“上次打印”属性？
答：要使用 Aspose.Words for .NET 更新 PDF 文档中的“上次打印”属性，请按照以下步骤操作：

创建一个实例`Document`指定 Word 文档路径的类。

创建一个实例`PdfSaveOptions`类并设置`UpdateLastPrintedProperty`财产`true`以启用更新“上次打印”属性。

使用`Save`方法`Document`通过指定保存选项将文档保存为 PDF 格式。

#### 问：如何检查生成的 PDF 文档中的“上次打印”属性是否已更新？
答：您可以使用兼容的 PDF 查看器（例如 Adobe Acrobat Reader）打开 PDF 文件并查看文档信息，检查生成的 PDF 文档中的“上次打印”属性是否已更新。上次打印的日期和时间应与 PDF 文档的生成日期和时间相对应。
