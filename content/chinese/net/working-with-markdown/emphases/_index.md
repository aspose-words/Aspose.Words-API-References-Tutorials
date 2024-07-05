---
title: 重点
linktitle: 重点
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 分步指南使用强调（粗体和斜体）。
type: docs
weight: 10
url: /zh/net/working-with-markdown/emphases/
---

在这个例子中，我们将解释如何在 Aspose.Words for .NET 中使用强调。强调用于强调文本的某些部分，例如粗体和斜体。

## 步骤 1：文档初始化

首先，我们将通过创建`Document`班级。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 第 2 步：使用文档生成器

接下来，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：添加带强调的文本

我们可以通过更改文档生成器的字体属性来添加强调文本。在此示例中，我们使用粗体和斜体来强调文本的不同部分。

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

## 步骤 4：保存文档

最后，我们可以将文档保存为所需的格式。在此示例中，我们使用`.md`Markdown 格式的扩展。

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

恭喜！您现在已经学会了如何使用 Aspose.Words for .NET 强调。

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

### 常见问题解答

#### 问：如何使用 Markdown 突出显示文本？

答：要使用 Markdown 突出显示文本，只需用适当的符号包围文本即可。使用`*`或者`_`斜体，`**`或者`__`为粗体，以及`~~`表示删除线。

#### 问：我们可以在同一篇文章中组合不同的亮点吗？

答：可以，可以在同一文本中组合不同的突出显示。例如，你可以同时使用粗体和斜体来加粗和斜体一个单词`**`和`*`围绕这个词。

#### 问：Markdown 中有哪些突出显示选项？

答：Markdown 中可用的突出显示选项是斜体（`*`或者`_`）， 大胆的 （`**`或者`__`）和删除线（`~~`）。

#### 问：如何处理文本中包含 Markdown 用于突出显示的特殊字符的情况？

答：如果你的文本包含 Markdown 用于突出显示的特殊字符，你可以在这些字符前加上`\`。 例如，`\*`将显示一个文字星号。

#### 问：我们可以使用 CSS 自定义突出显示的外观吗？

答：Markdown 中的高亮通常使用浏览器的默认样式进行呈现。如果您将 Markdown 转换为 HTML，则可以使用 CSS 规则自定义高亮的外观。