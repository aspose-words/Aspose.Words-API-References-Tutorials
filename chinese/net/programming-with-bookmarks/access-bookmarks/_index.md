---
title: 访问书签
linktitle: 访问书签
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 访问 Word 文档中的书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/access-bookmarks/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Access Bookmarks 功能。此功能提供对 Word 文档中特定书签的访问。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：加载文档

在开始访问书签之前，我们需要使用 Aspose.Words for .NET 加载 Word 文档。这可以通过实例化一个来完成`Document`指定文档文件路径的对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 第 2 步：访问书签

加载文档后，我们就可以访问文档中的书签。有两种方法可以访问书签：按索引和按名称。

- 通过索引访问：在我们的示例中，我们使用索引 0 来访问文档的第一个书签：

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- 按名称访问：在我们的示例中，我们使用名称“MyBookmark3”来访问文档中的特定书签：

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### 使用 Aspose.Words for .NET 访问书签的示例源代码

以下是演示使用 Aspose.Words for .NET 访问书签的完整示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	//按索引：
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	//按名字：
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的访问书签功能。我们按照分步指南上传文档并使用索引和名称访问书签。