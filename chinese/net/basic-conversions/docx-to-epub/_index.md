---
title: Docx 到 Epub
linktitle: Docx 到 Epub
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档从 Docx 格式转换为 Epub 格式。带示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/docx-to-epub/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将 Docx 格式的 Word 文档转换为 Epub 格式。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，你需要初始化`Document`通过以 Docx 格式提供源文档的路径来反对。代替`"YOUR DOCUMENT DIRECTORY"`使用文档所在的实际目录路径，以及`"Document.docx"`与您的源文档的名称。这是代码片段：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 第 2 步：将文档转换为 Epub 格式

接下来，您可以继续进行转换过程。打电话给`Save`上的方法`Document`对象并提供 Epub 格式输出文档的路径和文件名。在这个例子中，我们将它保存为`"BaseConversions.DocxToEpub.epub"`.这是代码片段：

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将 Docx 格式的 Word 文档转换为 Epub 格式。

### 使用 Aspose.Words for .NET 的 Docx To Epub 示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。