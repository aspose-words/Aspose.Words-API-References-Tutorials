---
title: 设置尾注选项
linktitle: 设置尾注选项
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置尾注选项。带示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/working-with-footnote-and-endnote/set-endnote-options/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 在 Word 文档中设置尾注选项。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供源文档的路径来反对：

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

使用`Write`的方法`DocumentBuilder`向文档中添加文本的对象，以及`InsertFootnote`插入尾注的方法：

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## 第 4 步：设置尾注选项

访问`EndnoteOptions`修改尾注选项的文档属性。在这个例子中，我们将重启规则设置为在每个页面上重启，并将位置设置为该部分的末尾：

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## 第 5 步：保存文档

最后，保存修改后的文件：

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

就是这样！您已经成功地使用 Aspose.Words for .NET 在 Word 文档中设置了尾注选项。

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

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。
