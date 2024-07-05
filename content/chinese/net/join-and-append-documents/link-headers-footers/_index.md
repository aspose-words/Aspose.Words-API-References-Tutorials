---
title: 链接页眉页脚
linktitle: 链接页眉页脚
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 合并和附加 Word 文档时链接页眉和页脚。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/link-headers-footers/
---

本教程将指导您完成使用 Aspose.Words for .NET 的“链接页眉页脚”功能的过程。此功能允许您合并和附加多个 Word 文档，同时将源文档的页眉和页脚链接到目标文档中的上一节。

## 先决条件

开始之前，请确保您已准备好以下物品：

1. 已安装 Aspose.Words for .NET。您可以从 Aspose 网站下载它或通过 NuGet 安装它。
2. Visual Studio 或任何其他 C# 开发环境。

## 步骤 1：初始化文档目录

首先，您需要设置文档目录的路径。修改`dataDir`变量为您的文档所在的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载源文档和目标文档

接下来，您需要使用 Aspose.Words 加载源文档和目标文档`Document`类。更新`Document`根据您的文档名称构造函数。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：将附加文档设置为显示在新页面上

为了确保源文档的内容出现在目标文档的新页面上，您需要设置`SectionStart`源文档第一节的属性`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 步骤 4：将页眉和页脚链接到上一节

要将源文档的页眉和页脚链接到目标文档中的上一节，可以使用`LinkToPrevious`方法`HeadersFooters`集合。通过传递`true`作为参数，您可以覆盖源文档中任何现有的页眉或页脚。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## 步骤 5：将源文档附加到目标文档

现在，您可以使用`AppendDocument`方法`Document`类。`ImportFormatMode.KeepSourceFormatting`参数确保在附加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 6：保存最终文档

最后，使用`Save`方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### 使用 Aspose.Words for .NET 的 Link Headers Footers 示例源代码 

以下是使用 Aspose.Words for .NET 的 C# 中的“链接页眉页脚”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//将附加的文档设置为出现在新页面上。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	//将源文档中的页眉和页脚链接到上一节。
	//这将覆盖源文档中已找到的任何页眉或页脚。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 实现了“链接页眉页脚”功能。最终文档将包含合并的内容，其中源文档的页眉和页脚链接到目标文档中的上一节。