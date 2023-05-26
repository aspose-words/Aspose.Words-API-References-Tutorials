---
title: 显示隐藏书签
linktitle: 显示隐藏书签
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 显示或隐藏文档中的特定书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/show-hide-bookmarks/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的显示隐藏书签功能。此功能允许您显示或隐藏文档中的特定书签。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：装入文档

我们使用`Document`从文件加载现有文档的类：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 第 2 步：显示或隐藏特定书签

我们使用`ShowHideBookmarkedContent`显示或隐藏文档中特定书签的函数。此函数将文档、书签名称和一个布尔值作为参数，以指示是否显示或隐藏书签：

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## 第 3 步：保存修改后的文档

我们使用`Save`将修改后的文档保存到文件的方法：

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### 使用 Aspose.Words for .NET 显示隐藏书签的示例源代码

以下是演示使用 Aspose.Words for .NET 显示或隐藏特定书签的完整示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## 结论

在本文中，我们探索了 C# 源代码以了解如何使用 Aspose.Words for .NET 的显示隐藏书签功能。我们按照分步指南显示或隐藏文档中的特定书签。