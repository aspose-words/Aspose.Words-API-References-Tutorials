---
title: 移至文档开始结束
linktitle: 移至文档开始结束
second_title: Aspose.Words for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.Words for .NET 在 Word 文档中移动到文档开头和结尾。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/move-to-document-start-end/
---

在此示例中，我们将探索 Aspose.Words for .NET 的“移至文档开始/结束”功能。 Aspose.Words 是一个功能强大的文档操作库，允许开发人员以编程方式创建、修改和转换 Word 文档。 “移至文档开始/结束”功能使我们能够使用 DocumentBuilder 类导航到文档的开头或结尾。

## 一步步解释源码

让我们逐步浏览源代码，了解如何使用 Aspose.Words for .NET 使用“移至文档开始/结束”功能。


## 步骤 1：初始化文档和文档生成器

接下来，初始化 Document 和 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：移至文档开头

要将光标位置移动到文档的开头，请使用 DocumentBuilder 类的 MoveToDocumentStart 方法：

```csharp
builder.MoveToDocumentStart();
```

## 第 3 步：移至文档末尾

要将光标位置移动到文档末尾，请使用 DocumentBuilder 类的 MoveToDocumentEnd 方法：

```csharp
builder.MoveToDocumentEnd();
```

## 第四步：输出光标位置

您可以使用 Console.WriteLine 或任何其他所需的方法输出光标位置。例如：

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### 使用 Aspose.Words for .NET 移动到文档开始/结束的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//将光标位置移动到文档的开头。
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

//将光标位置移至文档末尾。
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## 结论

在此示例中，我们探索了 Aspose.Words for .NET 的“移至文档开始/结束”功能。我们学习了如何使用 DocumentBuilder 类导航到文档的开头和结尾。当以编程方式处理 Word 文档并需要在文档中的特定位置操作或插入内容时，此功能非常有用。