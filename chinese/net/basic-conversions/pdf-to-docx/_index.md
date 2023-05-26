---
title: PDF 转 Docx
linktitle: PDF 转 Docx
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 PDF 文档转换为 Docx 格式。带示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/pdf-to-docx/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将 PDF 文档转换为 Docx 格式。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

开始之前，请确保您已经在开发环境中安装并设置了 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供 PDF 文档的路径来反对：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## 第 2 步：将文档保存为 Docx 格式

接下来，通过调用将文档保存为 Docx 格式`Save`上的方法`Document`对象并提供输出 Docx 文档的路径和文件名：

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将 PDF 文档转换为 Docx 格式。

### 使用 Aspose.Words for .NET 的 Pdf To Docx 示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。