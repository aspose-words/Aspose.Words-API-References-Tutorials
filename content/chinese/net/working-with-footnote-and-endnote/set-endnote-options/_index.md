---
title: 设置尾注选项
linktitle: 设置尾注选项
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置尾注选项。带有示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/working-with-footnote-and-endnote/set-endnote-options/
---

在本分步教程中，我们将指导您如何使用 Aspose.Words for .NET 在 Word 文档中设置尾注选项。我们将解释提供的 C# 源代码并向您展示如何在您自己的项目中实现它。

首先，请确保已在开发环境中安装并设置了 Aspose.Words for .NET。如果尚未安装，请从以下位置下载并安装该库[Aspose.发布]https://releases.aspose.com/words/net/。

## 步骤 1：初始化文档对象

首先，初始化`Document`通过提供源文档的路径来获取对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 步骤2：初始化DocumentBuilder对象

接下来，初始化`DocumentBuilder`对象对文档执行操作：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：添加文本和尾注

使用`Write`方法`DocumentBuilder`对象向文档添加文本，以及`InsertFootnote`插入尾注的方法：

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## 步骤 4：设置尾注选项

访问`EndnoteOptions`属性来修改尾注选项。在此示例中，我们将重新启动规则设置为在每一页重新启动，并将位置设置为节的末尾：

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## 步骤5：保存文档

最后保存修改后的文档：

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

就这样！您已成功使用 Aspose.Words for .NET 在 Word 文档中设置尾注选项。

### 使用 Aspose.Words for .NET 设置 Endnote 选项的示例源代码

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

请随意在您自己的项目中使用此代码，并根据您的特定要求进行修改。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置尾注样式？

答：要在 Aspose.Words 中设置尾注样式，您可以使用`EndnoteOptions`类和`SeparatorNoteTextStyle`属性。您可以使用此属性指定尾注的字体样式、大小、颜色等。

#### 问：可以自定义文档中尾注的编号吗？

答：是的，可以自定义文档中尾注的编号。您可以使用`RestartRule`和`NumberStyle`的属性`EndnoteOptions`类来定义具体的重启规则和编号样式。

#### 问：如何在文档中定位尾注？

答：要在文档中定位尾注，您可以使用`Position`的财产`EndnoteOptions`类。您可以指定是否应将尾注放在每页的底部、每节的末尾或文档的末尾。

#### 问：我可以自定义尾注编号格式吗？

答：是的，您可以在 Aspose.Words 中自定义尾注编号的格式。使用`NumberFormat`的财产`EndnoteOptions`类来设置所需的格式，例如阿拉伯数字、罗马数字、字母等。

#### 问： 是否可以在文档的各个部分之间继续尾注编号？

答：是的，可以在文档的各节之间继续尾注编号。使用`RestartRule`的财产`EndnoteOptions`类并将其设置为`RestartContinuous`允许各部分之间继续编号。