---
title: 插入段落
linktitle: 插入段落
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入格式化段落。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-paragraph/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 将段落插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够向文档中添加格式化的段落。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：设置字体和格式
接下来，分别使用 Font 和 ParagraphFormat 对象设置字体属性和段落格式：

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## 第 3 步：插入段落
设置字体和格式后，使用 DocumentBuilder 类的 Writeln 方法插入整个段落：

```csharp
builder.Writeln("A whole paragraph.");
```

## 步骤 4：保存文档
插入段落后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## 使用 Aspose.Words for .NET 插入段落的示例源代码
以下是使用 Aspose.Words for .NET 插入段落的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## 结论
恭喜！您已成功学习如何使用 Aspose.Words for .NET 将格式化段落插入到 Word 文档中。通过遵循分步指南并利用提供的源代码，您现在可以向文档添加具有特定字体、格式和对齐方式的自定义段落。