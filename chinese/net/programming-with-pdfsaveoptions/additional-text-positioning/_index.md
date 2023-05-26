---
title: 附加文本定位
linktitle: 附加文本定位
second_title: Aspose.Words for .NET API 参考
description: 了解在使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 时如何控制附加文本的位置。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的附加文本定位功能的步骤。此功能允许您在将 Word 文档转换为 PDF 时控制附加文本的位置。请按照以下步骤操作：

## 第 1 步：装入文档

首先上传要转换为 PDF 的 Word 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定正确的 Word 文档路径。

## 第 2 步：设置 PDF 转换选项

创建 PdfSaveOptions 类的实例并启用额外的文本定位：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

此选项控制附加文本在 PDF 中的精确放置。

## 第 3 步：将文档转换为 PDF

使用`Save`通过指定转换选项将 Word 文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 的附加文本定位示例源代码

以下是使用 Aspose.Words for .NET 的附加文本定位功能的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
通过执行这些步骤，您可以在使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 时轻松控制附加文本的位置。

