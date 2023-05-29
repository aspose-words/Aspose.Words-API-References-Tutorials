---
title: 重点
linktitle: 重点
second_title: Aspose.Words for .NET API 参考
description: 通过 Aspose.Words for .NET 分步指南了解如何使用强调（粗体和斜体）。
type: docs
weight: 10
url: /zh/net/working-with-markdown/emphases/
---

在这个例子中，我们将解释如何在 Aspose.Words for .NET 中使用强调。强调用于强调文本的某些部分，例如粗体和斜体。

## 第一步：文档初始化

首先，我们将通过创建一个实例来初始化文档`Document`班级。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 第 2 步：使用文档生成器

接下来，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：添加带有重点的文本

我们可以通过更改文档生成器的字体属性来添加强调文本。在这个例子中，我们使用粗体和斜体来强调文本的不同部分。

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## 第 4 步：保存文档

最后，我们可以将文档保存为所需的格式。在这个例子中，我们使用`.md`Markdown 格式的扩展。

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

恭喜！您现在已经了解了如何在 Aspose.Words for .NET 中使用强调。

### 使用 Aspose.Words for .NET 的 Emphases 示例源代码


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```
