---
title: 文本标题
linktitle: 文本标题
second_title: Aspose.Words for .NET API 参考
description: 通过 Aspose.Words for .NET 分步指南了解如何使用 Setext 标题格式化您的文档。
type: docs
weight: 10
url: /zh/net/working-with-markdown/setext-heading/
---

在本教程中，我们将带您了解如何使用 Aspose.Words for .NET 的 Setext Heading 功能。 Setext Heading 是在 Markdown 文档中格式化标题的另一种方法。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：使用 Setext 标题样式

我们将使用默认的“标题 1”段落样式在我们的文档中创建一个 1 级标题。

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 第 3 步：重置样式

我们重置了以前应用的字体样式，以避免段落之间出现任何不需要的样式组合。

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 第 4 步：自定义 Setext 标题级别

我们可以通过在现有标题样式的基础上添加新的段落样式来自定义 Setext 标题级别。在此示例中，我们基于“标题 1”样式创建“SetextHeading1”样式，以表示 Setext 格式的 1 级标题。

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## 第 5 步：保存文档

最后，我们可以将文档保存为所需的格式。

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### 使用 Aspose.Words for .NET 的 Setext 标题示例源代码

```csharp
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//使用文档生成器向文档添加内容。
	DocumentBuilder builder = new DocumentBuilder();

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");

	//重置上一段的样式以不合并段落之间的样式。
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
	builder.ParagraphFormat.Style = setexHeading1;
	builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
	builder.Writeln("Setext Heading level 1");

	builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
	builder.Writeln("This is an H3 tag");

	//重置上一段的样式以不合并段落之间的样式。
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
	builder.ParagraphFormat.Style = setexHeading2;
	builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

	//如果基本段落的标题级别大于 2，Setex 标题级别将重置为 2。
	builder.Writeln("Setext Heading level 2");
	

	builder.Document.Save(dataDir + "Test.md");
```



