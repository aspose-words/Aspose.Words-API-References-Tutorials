---
title: 插入目录
linktitle: 插入目录
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入目录。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-table-of-contents/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 将目录插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够生成具有适当标题和页码的目录。

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

## 第 2 步：插入目录
接下来，使用 DocumentBuilder 类的 InsertTableOfContents 方法插入目录。在方法中指定所需的格式选项：

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 第三步：添加文档内容
插入目录后，添加实际的文档内容。使用 StyleIdentifier 设置适当的标题样式：

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## 第 4 步：更新目录
新插入的目录最初是空的。要填充它，请更新文档中的字段：

```csharp
doc.UpdateFields();
```

## 第 5 步：保存文档
插入目录并更新字段后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### 使用 Aspose.Words for .NET 插入目录的示例源代码
以下是使用 Aspose.Words for .NET 插入目录的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

//使用 Document 对象初始化 DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入目录a
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

//从第二页开始实际文档内容。
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


//新插入的目录最初是空的。
//需要通过更新文档中的字段来填充它。
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```
