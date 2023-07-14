---
title: 更新 PDF 文档中最后打印的属性
linktitle: 更新 PDF 文档中最后打印的属性
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 转换为 PDF 时更新“上次打印”属性的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

本文提供了有关如何通过 Aspose.Words for .NET 使用 PDF 文档更新功能中的“上次打印”属性的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何配置选项以在转换为 PDF 时更新“上次打印”属性。

在开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第1步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上传文件

接下来，我们需要加载我们想要处理的文档。在此示例中，我们假设文档名为“Rendering.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：使用更新的“上次打印”属性配置另存为 PDF 选项

要在转换为 PDF 时更新“上次打印”属性，我们需要配置`PdfSaveOptions`对象并设置`UpdateLastPrintedProperty`财产给`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## 步骤 4：将文档另存为 PDF，并更新“上次打印”属性

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

就这样 ！使用 Aspose.Words for .NET 将文档转换为 PDF 时，您已成功启用更新“上次打印”属性。

### 使用 Aspose.Words for .NET 更新“上次打印”属性的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 更新 PDF 文档中的“上次打印”属性。通过执行给定的步骤，您可以轻松配置选项以在将文档转换为 PDF 时更新“上次打印”属性。使用此功能可以跟踪文档使用情况和相关信息。

### 经常问的问题

#### 问：PDF 文档中的“最后打印”属性是什么？
答：PDF文档中的“上次打印”属性是指文档上次打印的日期和时间。此属性对于跟踪有关文档使用和管理的信息非常有用。

#### 问：如何使用 Aspose.Words for .NET 更新 PDF 文档中的“上次打印”属性？
答：要使用 Aspose.Words for .NET 更新 PDF 文档中的“上次打印”属性，请按照下列步骤操作：

创建一个实例`Document`指定 Word 文档路径的类。

创建一个实例`PdfSaveOptions`类并设置`UpdateLastPrintedProperty`财产给`true`启用更新“上次打印”属性。

使用`Save`的方法`Document`类通过指定保存选项将文档保存为 PDF 格式。

#### 问：如何检查生成的 PDF 文档中的“上次打印”属性是否已更新？
答：您可以通过使用兼容的 PDF 查看器（例如 Adobe Acrobat Reader）打开 PDF 文件并查看文档信息来检查生成的 PDF 文档中的“上次打印”属性是否已更新。最后打印的日期和时间应与生成 PDF 文档的日期和时间相对应。
