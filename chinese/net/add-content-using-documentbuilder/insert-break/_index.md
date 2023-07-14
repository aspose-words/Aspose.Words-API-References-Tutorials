---
title: 插入中断
linktitle: 插入中断
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入分页符。分步指南。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-break/
---

在这个综合示例中，您将学习如何使用 Aspose.Words for .NET 中的 InsertBreak 方法将分页符插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够控制文档中的分页符。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入内容和分页符
接下来，使用 DocumentBuilder 类的 Writeln 方法向文档添加内容。要插入分页符，请使用带有 BreakType.PageBreak 参数的 InsertBreak 方法：

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## 第 3 步：保存文档
插入内容和分页符后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### 使用 Aspose.Words for .NET 插入中断的示例源代码
以下是使用 Aspose.Words for .NET 插入分页符的完整源代码：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

请记住根据您的具体要求调整代码，并根据需要使用附加功能对其进行增强。


## 结论
恭喜！您已成功学习如何使用 Aspose.Words for .NET 将分页符插入到 Word 文档中。通过遵循分步指南并利用提供的源代码，您现在可以通过在所需位置插入分页符来控制文档的分页和布局。
