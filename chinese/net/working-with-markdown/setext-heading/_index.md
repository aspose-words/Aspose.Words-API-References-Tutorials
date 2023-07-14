---
title: 固定文本标题
linktitle: 固定文本标题
second_title: Aspose.Words 文档处理 API
description: 通过 Aspose.Words for .NET 分步指南了解如何使用 Setext 标题来格式化文档。
type: docs
weight: 10
url: /zh/net/working-with-markdown/setext-heading/
---

在本教程中，我们将引导您了解如何将 Setext 标题功能与 Aspose.Words for .NET 一起使用。 Setext 标题是在 Markdown 文档中格式化标题的另一种方法。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：使用 Settext 标题样式

我们将使用默认的“标题 1”段落样式在文档中创建 1 级标题。

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 第三步：重置样式

我们重置了之前应用的字体样式，以避免段落之间出现任何不需要的样式组合。

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 第 4 步：自定义 Setext 标题级别

我们可以通过基于现有标题样式添加新的段落样式来自定义 Setext 标题级别。在此示例中，我们将基于“Heading 1”样式创建“SetextHeading1”样式，以表示 Setext 格式中的 1 级标题。

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

### 使用 Aspose.Words for .NET 的 Setext 标题的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

//重置上一段的样式，以不合并段落之间的样式。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

//重置上一段的样式，以不合并段落之间的样式。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

//如果基本段落的标题级别大于 2，Setex 标题级别将重置为 2。
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### 常见问题解答

#### 问：什么是 Setext Markdown 标头？

答：Setext Markdown 标题是在 Markdown 文档中创建标题的另一种方法。它使用下划线字符（= 或 -）来指示不同级别的标题。

#### 问：如何使用 Setext Markdown 标题？

答：要使用 Setext Markdown 标题，请将下划线放在标题文本下方。对于 1 级标题使用等号 (=)，对于 2 级标题使用连字符 (-)。

#### 问：使用 Setext Markdown 标头有什么限制吗？

答：Setext Markdown 标题在标题层次结构方面存在限制，并且在视觉上不像标准 Markdown 标题那样明显。

#### 问：我可以自定义 Setext Markdown 标题的外观吗？

答：在标准 Markdown 中，无法自定义 Setext Markdown 标题的外观。它们具有基于所使用的下划线字符的预定义外观。

#### 问：所有 Markdown 编辑器都支持 Setext Markdown 标头吗？

答：不同 Markdown 编辑器对 Setext Markdown 标头的支持可能有所不同。请检查您的发布商的具体文档以确保确定。