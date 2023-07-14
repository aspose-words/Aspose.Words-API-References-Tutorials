---
title: 设置尾注选项
linktitle: 设置尾注选项
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置尾注选项。带有示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/working-with-footnote-and-endnote/set-endnote-options/
---

在本分步教程中，我们将指导您如何使用 Aspose.Words for .NET 在 Word 文档中设置尾注选项。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

首先，请确保您已在开发环境中安装并设置了 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供源文档的路径来对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 第 2 步：初始化 DocumentBuilder 对象

接下来，初始化`DocumentBuilder`对文档执行操作的对象：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：添加文本和尾注

使用`Write`的方法`DocumentBuilder`向文档添加文本的对象，以及`InsertFootnote`插入尾注的方法：

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## 第 4 步：设置尾注选项

访问`EndnoteOptions`文档的属性来修改尾注选项。在本例中，我们将重启规则设置为在每个页面上重新启动，并将位置设置为该部分的末尾：

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## 第 5 步：保存文档

最后保存修改后的文档：

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

就是这样！您已使用 Aspose.Words for .NET 在 Word 文档中成功设置尾注选项。

### 使用 Aspose.Words for .NET 设置尾注选项的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

请随意在您自己的项目中使用此代码，并根据您的具体要求进行修改。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置尾注样式？

答：要在 Aspose.Words 中设置尾注样式，您可以使用`EndnoteOptions`类和`SeparatorNoteTextStyle`财产。您可以使用此属性指定尾注的字体样式、大小、颜色等。

#### 问：是否可以自定义文档中尾注的编号？

答：是的，可以自定义文档中尾注的编号。您可以使用`RestartRule`和`NumberStyle`的属性`EndnoteOptions`类来定义特定的重新启动规则和编号样式。

#### 问：如何在文档中放置尾注？

答：要在文档中放置尾注，您可以使用`Position`的财产`EndnoteOptions`班级。您可以指定尾注是否应放置在每页的底部、每个部分的末尾或文档的末尾。

#### 问：我可以自定义尾注编号格式吗？

答：是的，您可以在 Aspose.Words 中自定义尾注编号的格式。使用`NumberFormat`的财产`EndnoteOptions`class 来设置所需的格式，如阿拉伯数字、罗马数字、字母等。

#### 问：是否可以在文档各部分之间继续进行尾注编号？

答：是的，可以在文档各部分之间继续进行尾注编号。使用`RestartRule`的财产`EndnoteOptions`类并将其设置为`RestartContinuous`允许在各节之间继续编号。