---
title: 在 Word 文档中按书签删除行
linktitle: 在 Word 文档中按书签删除行
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 根据 Word 文档中的特定书签删除表格行。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/delete-row-by-bookmark/
---

在本文中，我们将探索上述 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的按书签删除行功能。此功能允许您根据 Word 文档中的特定书签删除表格行。

## 先决条件

- C# 语言的基本知识。
- 安装了 Aspose.Words 库的.NET 开发环境。

## 步骤 1：获取书签

我们使用`Bookmarks`文档范围的属性来获取我们想要用来删除表行的特定书签：

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## 步骤 2：删除表格行

我们使用`GetAncestor`方法获取`Row`书签的父元素。接下来，我们使用`Remove`删除表格行的方法：

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### 使用 Aspose.Words for .NET 按书签删除行的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 根据特定书签删除表格行：

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的按书签删除行功能。我们按照分步指南根据文档中的特定书签删除表格行。

### 关于word文档中按书签删除行的常见问题

#### 问：我可以使用同一个书签删除多行吗？

答：是的，您可以使用同一个书签删除多行。但是，您需要处理代码中的逻辑来确定要删除的行数，并对提供的代码片段进行必要的调整。

#### 问：如果文档中不存在书签会发生什么情况？

答：如果文档中不存在指定的书签，代码片段将返回书签对象的空值。因此，您需要在代码中处理这种情况，方法是在尝试删除表行之前添加适当的检查。

#### 问：Aspose.Words 库可以免费使用吗？

答：Aspose.Words 库是一个商业库，您可能需要有效的许可证才能在项目中使用它。您可以访问[Aspose.Words for .NET API 参考](https://reference.aspose.com/words/net/)了解有关其许可选项和定价的更多信息。

#### 问：我可以从 Word 文档特定部分的表格中删除行吗？

答：是的，您可以从 Word 文档特定部分中的表格中删除行。您可以修改提供的代码片段，以使用该部分中的适当范围或书签来定位特定部分。