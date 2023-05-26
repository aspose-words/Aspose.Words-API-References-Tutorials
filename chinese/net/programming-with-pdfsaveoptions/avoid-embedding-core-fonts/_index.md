---
title: 避免嵌入核心字体
linktitle: 避免嵌入核心字体
second_title: Aspose.Words for .NET API 参考
description: 了解在使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 时如何避免基本字体嵌入。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的避免基本字体嵌入功能的步骤。此功能允许您控制在转换 Word 文档时是否必须在 PDF 中嵌入 Arial、Times New Roman 等基本字体。请按照以下步骤操作：

## 第 1 步：装入文档

首先上传要转换为 PDF 的 Word 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定正确的 Word 文档路径。

## 第 2 步：设置 PDF 转换选项

创建 PdfSaveOptions 类的实例并启用基本字体嵌入避免：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

此选项控制基本字体是否应嵌入 PDF 中。

## 第 3 步：将文档转换为 PDF

使用`Save`通过指定转换选项将 Word 文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 避免嵌入核心字体的示例源代码

下面是使用 Aspose.Words for .NET 避免核心字体嵌入功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//输出的 PDF 不会嵌入 Arial、Times New Roman 等核心字体。
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

通过执行这些步骤，您可以轻松地控制在使用 Aspose.Words for .NET 转换 Word 文档时是否应将基本字体嵌入到 PDF 中。

