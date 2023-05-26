---
title: 按页面范围
linktitle: 按页面范围
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 分步指南轻松按页面范围从 Word 文档中提取。
type: docs
weight: 10
url: /zh/net/split-document/by-page-range/
---

## 介绍
在本教程中，我们将逐步引导您了解和使用 Aspose.Words for .NET 的“按页面范围”功能。此功能允许您使用给定的页面范围提取大型 Word 文档的特定部分。我们会为您提供完整的源代码和Markdown输出格式，方便您以后的理解和使用。

## 要求
在开始之前，请确保您已具备以下条件：

1. Aspose.Words for .NET 安装在你的开发机器上。
2. 要从中提取特定部分的大型 Word 文件。

现在我们已经涵盖了这些要求，我们可以继续使用“按页面范围”功能的步骤。

## 第一步：文档初始化和加载
设置开发环境后，您需要初始化并加载要从中提取特定部分的 Word 文档。这是要使用的代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

请务必将“YOUR_DOCUMENTS_DIRECTORY”替换为文档目录的实际路径，并将“Name_of_large_document.docx”替换为大型 Word 文件的名称。

## 第二步：提取文档的一部分
现在我们已经加载了文档，我们可以使用`ExtractPages`功能与所需的页面范围。方法如下：

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

在此示例中，我们从原始文档中提取第 3-6 页。您可以根据需要调整页码。

## 第三步：保存提取的部分
一旦我们提取了所需的页面，我们就可以将它们保存在一个新的 Word 文档中。就是这样：

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

请务必将“Document_Extraits.ParPlageDePages.docx”替换为您的输出文件所需的名称。

### 使用 Aspose.Words for .NET 的按页面范围示例源代码

```csharp

            //文档目录的路径。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(MyDir + "Big document.docx");
            
            //获取文档的一部分。
            Document extractedPages = doc.ExtractPages(3, 6);
            extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
            
        
```

## 结论
恭喜！您已经学习了如何使用 Aspose.Words for .NET 中的“按页面范围”。现在，您可以使用给定的页面范围轻松提取大型 Word 文档的特定部分。随意尝试更多 Aspose 的其他强大功能。 .Words 满足您的特定需求。

