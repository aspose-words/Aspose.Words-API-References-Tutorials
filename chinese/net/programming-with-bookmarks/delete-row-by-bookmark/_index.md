---
title: 按书签删除行
linktitle: 按书签删除行
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 根据文档中的特定书签删除表格行。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/delete-row-by-bookmark/
---

在本文中，我们将探索上述 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的按书签删除行功能。此功能允许您根据文档中的特定书签删除表格行。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第一步：获取书签

我们使用`Bookmarks`文档范围的属性来获取我们要用来删除表行的特定书签：

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## 步骤 2：删除表格行

我们使用`GetAncestor`方法得到`Row`输入书签的父元素。接下来，我们使用`Remove`删除表格行的方法：

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### 使用 Aspose.Words for .NET 按书签删除行的示例源代码

以下是完整的示例源代码，演示使用 Aspose.Words for .NET 删除基于特定书签的表格行：

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的按书签删除行功能。我们按照分步指南根据文档中的特定书签删除表格行。