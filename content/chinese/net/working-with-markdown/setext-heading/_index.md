---
title: Setext 标题
linktitle: Setext 标题
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Setext 标题通过 Aspose.Words for .NET 分步指南来格式化您的文档。
type: docs
weight: 10
url: /zh/net/working-with-markdown/setext-heading/
---

在本教程中，我们将引导您了解如何将 Setext 标题功能与 Aspose.Words for .NET 结合使用。Setext 标题是 Markdown 文档中格式化标题的另一种方法。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：使用 Setext 标题样式

我们将使用默认的“标题 1”段落样式在文档中创建 1 级标题。

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 步骤 3：重置样式

我们重置了之前应用的字体样式，以避免段落之间出现任何不必要的样式组合。

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 步骤 4：自定义 Setext 标题级别

我们可以通过在现有标题样式的基础上添加新的段落样式来自定义 Setext 标题级别。在此示例中，我们基于“标题 1”样式创建“SetextHeading1”样式，以表示 Setext 格式的 1 级标题。

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## 步骤 5：保存文档

最后，我们可以以所需的格式保存文档。

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

//重置上一段的样式，以免段落之间合并样式。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

//重置上一段的样式，以免段落之间合并样式。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

//如果基本段落的标题级别大于 2，则 Setex 标题级别将重置为 2。
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### 常见问题解答

#### 问：什么是 Setext Markdown 标题？

答：Setext Markdown 标题是 Markdown 文档中创建标题的另一种方式。它使用下划线字符（= 或 -）来表示不同级别的标题。

#### 问：如何使用 Setext Markdown 标题？

答：要使用 Setext Markdown 标题，请在标题文本下方放置下划线。使用等号 (=) 表示一级标题，使用连字符 (-) 表示二级标题。

#### 问：使用 Setext Markdown 标题有什么限制吗？

答：Setext Markdown 标题在标题层次方面存在限制，并且在视觉上不如标准 Markdown 标题那么鲜明。

#### 问：我可以自定义 Setext Markdown 标题的外观吗？

答：在标准 Markdown 中，无法自定义 Setext Markdown 标题的外观。它们具有基于所使用的下划线字符的预定义外观。

#### 问：所有 Markdown 编辑器都支持 Setext Markdown 标题吗？

答：不同 Markdown 编辑器对 Setext Markdown 标题的支持可能有所不同。请查看发布商的具体文档以确保无误。