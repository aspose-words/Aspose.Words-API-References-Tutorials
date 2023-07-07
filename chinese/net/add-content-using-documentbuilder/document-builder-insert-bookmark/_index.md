---
title: 文档生成器插入书签
linktitle: 文档生成器插入书签
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 中的 DocumentBuilder 在 Word 文档中插入书签。分步指南。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

在这个综合示例中，您将学习如何使用 Aspose.Words for .NET 中的 DocumentBuilder 类将书签插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够在文档中创建和管理书签。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入书签
接下来，使用 DocumentBuilder 类的 StartBookmark 和 EndBookmark 方法将书签插入到文档中。为书签提供唯一的名称作为参数：

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## 第 3 步：保存文档
插入书签后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### DocumentBuilder 的示例源代码使用 Aspose.Words for .NET 插入书签
以下是使用 Aspose.Words for .NET 中的 DocumentBuilder 类插入书签的完整源代码：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

## 结论
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 中的 DocumentBuilder 类将书签插入到 Word 文档中。通过遵循分步指南并利用提供的源代码，您现在可以在文档中创建和管理书签。

书签对于各种场景都很有用，例如浏览大型文档、引用特定部分或以编程方式操作书签区域内的内容。

请记住根据您的具体要求调整代码，并根据需要使用附加功能对其进行增强。

