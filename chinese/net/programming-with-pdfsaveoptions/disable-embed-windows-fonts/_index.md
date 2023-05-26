---
title: 禁用嵌入 Windows 字体
linktitle: 禁用嵌入 Windows 字体
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 将文档转换为 PDF 时禁用 Windows 字体嵌入。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 禁用 PDF 文档中的 Windows 字体嵌入的步骤。通过禁用字体嵌入，您可以减小生成的 PDF 文件的大小。请按照以下步骤操作：

## 第 1 步：装入文档

首先上传要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定文档的正确路径。

## 第 2 步：设置 PDF 保存选项

创建 PdfSaveOptions 类的实例并指定如何嵌入字体：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

此选项允许您在生成的 PDF 文件中停用 Windows 字体的集成。

## 第 3 步：将文档转换为 PDF

使用`Save`指定转换选项将文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 禁用嵌入 Windows 字体的示例源代码

以下是使用 Aspose.Words for .NET 禁用在 PDF 文档中嵌入 Windows 字体的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//输出的 PDF 将在不嵌入标准 Windows 字体的情况下保存。
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
按照这些步骤，您可以使用 Aspose.Words for .NET 轻松禁用 Windows 字体在 PDF 文档中的嵌入。

