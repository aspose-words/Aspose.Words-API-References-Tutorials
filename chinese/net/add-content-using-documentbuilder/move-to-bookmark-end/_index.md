---
title: 移至书签末尾
linktitle: 移至书签末尾
second_title: Aspose.Words for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.Words for .NET 移动到 Word 文档中书签的末尾。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/move-to-bookmark-end/
---

在这个例子中，我们将探索 Aspose.Words for .NET 的 Move To Bookmark End 特性。 Aspose.Words 是一个强大的文档操作库，使开发人员能够以编程方式创建、修改和转换 Word 文档。移动到书签末尾功能允许我们导航到文档中特定书签的末尾并在其后添加内容。

## 设置环境

在我们深入研究实现细节之前，让我们确保我们已经设置了必要的环境来使用 Aspose.Words for .NET。确保您具有以下内容：

- Aspose.Words for .NET 库的有效安装
- C#编程语言的基础知识
- 访问 .NET 开发环境

## 了解 Aspose.Words for .NET 的移动到书签结束功能

移动到书签末尾功能允许您使用 Aspose.Words for .NET 导航到 Word 文档中书签的末尾。当您想要以编程方式在文档中的特定书签后添加内容时，此功能非常有用。

## 逐步解释源代码

让我们逐步分解提供的源代码，以了解如何使用 Aspose.Words for .NET 中的移动到书签结束功能。

## 第 1 步：初始化文档和文档生成器

首先，我们需要初始化`Document`和`DocumentBuilder`对象：

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：移动到书签末尾

要移动到书签的末尾，请使用`MoveToBookmark`的方法`DocumentBuilder`班级：

```csharp
builder.MoveToBookmark("MyBookmark1", false, true);
```

这`MoveToBookmark`方法接受三个参数：
- 书签名称：提供您要移动到的书签的名称。
-  IsBookmarkStart：设置为`false`移动到书签的末尾。
-  IsBookmarkEnd：设置为`true`表示您要移至书签末尾。

## 第三步：在书签末尾添加内容

移动到书签端后，您可以使用`DocumentBuilder`班级。在这个例子中，我们使用`Writeln`写一行文字的方法：

```csharp
builder.Writeln("This is a bookmark.");
```

这`Writeln`方法将指定文本作为新段落附加到`DocumentBuilder`.

### 使用 Aspose.Words for .NET 移动到书签结尾的示例源代码

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToBookmark("MyBookmark1", false, true);
builder.Writeln("This is a bookmark.");
```

## 结论

我们探索了 Aspose.Words for .NET 的 Move To Bookmark End 特性。我们学习了如何导航到书签的末尾并使用提供的源代码以编程方式添加内容。此功能为使用 Aspose.Words for .NET 操作 Word 文档提供了灵活性。

