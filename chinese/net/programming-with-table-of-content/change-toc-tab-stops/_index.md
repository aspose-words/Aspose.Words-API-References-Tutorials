---
title: 更改目录制表位
linktitle: 更改目录制表位
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 更改 Word 文档中的目录选项卡。
type: docs
weight: 10
url: /zh/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET 是一个功能强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。在 Aspose.Words 提供的功能中，可以修改 Word 文档目录中使用的选项卡。在本指南中，我们将向您展示如何使用 Aspose.Words for .NET 的 C# 源代码来更改文档目录中的选项卡。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个流行的库，它使 Word 文档的处理变得简单而高效。它提供了用于创建、编辑和操作 Word 文档的广泛功能，包括更改目录选项卡。

## 加载包含目录的文档

第一步是加载包含要修改目录的 Word 文档。使用 Document 类从源文件加载文档。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

在此示例中，我们加载位于文档目录中的文档“Table ofcontents.docx”。

## 更改目录中的选项卡

加载文档后，我们将浏览文档的每个段落并检查其是否使用目录 (TOC) 结果样式进行格式化。如果是这样，我们修改用于对齐页码的选项卡。就是这样：

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

在此示例中，我们使用循环来循环遍历文档中的每个段落。然后，我们检查该段落是否使用目录结果 (TOC) 样式进行格式化。如果是这样，我们访问本段中使用的第一个选项卡，并通过删除旧选项卡并添加具有修改位置的新选项卡来修改它。

## 保存修改后的文档

对目录中的选项卡进行必要的更改后，可以使用 Document 类的 Save 方法保存修改后的文档。这是一个例子：

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

在此示例中，我们将修改后的文档保存为“WorkingWithTableOfContent.ChangeTocTabStops.docx”。

### Aspose.Words for .NET 的“编辑目录选项卡”功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载包含目录的文档
Document doc = new Document(dataDir + "Table of contents.docx");

//修改目录的选项卡
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

//保存修改后的文档
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## 结论

在本指南中，我们介绍了如何使用 Aspose.Words for .NET 使用提供的 C# 源代码更改 Word 文档目录中的选项卡。通过按照提供的步骤操作，您可以轻松地在 C# 应用程序中自定义 Word 文档中的目录选项卡。 Aspose.Words 提供了巨大的灵活性和强大的功能来处理文档的样式和格式，使您能够创建有吸引力且专业的 Word 文档。