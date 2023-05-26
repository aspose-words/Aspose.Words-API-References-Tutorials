---
title: 设置脚注和尾注位置
linktitle: 设置脚注和尾注位置
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置脚注和尾注的位置。
type: docs
weight: 10
url: /zh/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 在 Word 文档中设置脚注和尾注的位置。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

开始之前，请确保您已经在开发环境中安装并设置了 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供源文档的路径来反对：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## 第二步：设置脚注和尾注位置

接下来，访问`FootnoteOptions`和`EndnoteOptions`文档的属性来设置脚注和尾注的位置。在此示例中，我们将脚注的位置设置在文本下方，将尾注的位置设置在该节的末尾：

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## 第 3 步：保存文档

最后，保存修改后的文件：

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功设置了 Word 文档中脚注和尾注的位置。

### 使用 Aspose.Words for .NET 设置脚注和尾注位置的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。
