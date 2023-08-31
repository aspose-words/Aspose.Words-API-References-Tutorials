---
title: 在 Word 文档中复制添加书签的文本
linktitle: 在 Word 文档中复制添加书签的文本
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档中的书签文本复制到另一个文档。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/copy-bookmarked-text/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的复制书签文本功能。此功能允许您将特定书签的内容从源文档复制到另一个文档。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第1步：加载源文档

在复制书签文本之前，我们需要将源文档加载到`Document`使用文件路径的对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## 第二步：获取源书签

我们使用`Bookmarks`源文档范围的属性来获取我们要复制的特定书签：

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## 步骤 3：创建目标文档

我们创建一个新文档作为复制书签内容的目标文档：

```csharp
Document dstDoc = new Document();
```

## 步骤 4：指定复制位置

我们指定要添加复制文本的位置。在我们的示例中，我们将文本添加到目标文档最后一部分的正文末尾：

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 第 5 步：导入并复制书签文本

我们使用一个`NodeImporter`对象将书签文本从源文档导入并复制到目标文档：

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### 使用 Aspose.Words for .NET 复制书签文本的示例源代码

以下是演示使用 Aspose.Words for .NET 从书签复制文本的完整示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	//这是我们要复制其内容的书签。
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	//我们将添加到此文档中。
	Document dstDoc = new Document();

	//假设我们将附加到最后一节正文的末尾。
	CompositeNode dstNode = dstDoc.LastSection.Body;

	//如果在没有单个上下文的情况下多次导入，将导致创建许多样式。
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用从 Aspose.Words for .NET 复制书签文本的功能。我们按照分步指南将书签的内容从源文档复制到另一个文档。

### 在 Word 文档中复制书签文本的常见问题解答

#### 问：使用 Aspose.Words for .NET 中的“复制带有书签的文本”功能有什么要求？

答：要使用 Aspose.Words for .NET 中的“复制带有书签的文本”功能，您需要具备 C# 语言的基础知识。您还需要一个安装了 Aspose.Words 库的 .NET 开发环境。

#### 问：如何将源文档加载到 Aspose.Words for .NET 中？

答：要在 Aspose.Words for .NET 中加载源文档，您可以使用`Document`通过指定文档的文件路径来定义类。这是示例代码：

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### 问：如何使用 Aspose.Words for .NET 获取源文档中特定书签的内容？

答：要使用 Aspose.Words for .NET 获取源文档中特定书签的内容，您可以访问`Bookmarks`源文档范围的属性并使用书签名称来检索特定的书签。这是示例代码：

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### 问：如何使用 Aspose.Words for .NET 指定目标文档中书签文本副本的位置？

答：要使用 Aspose.Words for .NET 指定要在目标文档中添加复制的书签文本的位置，您可以导航到目标文档最后一部分的正文。您可以使用`LastSection`属性来访问最后一部分和`Body`属性来访问该部分的主体。这是示例代码：

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### 问：如何使用 Aspose.Words for .NET 将书签文本从源文档导入并复制到目标文档？

答：要使用 Aspose.Words for .NET 将书签文本从源文档导入并复制到目标文档，您可以使用`NodeImporter`指定源文档、目标文档和要保留的格式模式的类。然后您可以使用`AppendBookmarkedText`方法在目标文档中添加书签文本。这是示例代码：

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### 问：使用 Aspose.Words for .NET 复制书签文本后如何保存目标文档？

答：要使用 Aspose.Words for .NET 从书签复制文本后保存目标文档，您可以使用`Save`的方法`Document`指定目标文件路径的对象。这是示例代码：

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```