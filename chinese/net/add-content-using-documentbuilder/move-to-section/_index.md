---
title: 移动到部分
linktitle: 移动到部分
second_title: Aspose.Words for .NET API 参考
description: 在 Aspose.Words for .NET 中使用移动到部分的分步指南操作 Word 文档中的部分和段落。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/move-to-section/
---

在本示例中，我们将使用提供的 C# 源代码逐步指导您如何使用 Aspose.Words for .NET 的移动到部分功能。此功能允许您在 Word 文档中导航和操作不同的部分。按照以下步骤将此功能集成到您的应用程序中。

## 第 1 步：创建一个新文档并添加一个部分

首先，我们需要创建一个新文档并向其中添加一个部分。使用以下代码完成此步骤：

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

此代码创建一个新的空文档并向该文档添加一个部分。

## 第 2 步：将 DocumentBuilder 移至第二部分并添加文本

接下来，我们需要将 DocumentBuilder 移动到文档的第二部分并在那里添加一些文本。使用以下代码执行此步骤：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

此代码从现有文档创建一个 DocumentBuilder，然后将光标从 DocumentBuilder 移动到文档的第二部分。最后，它将指定的文本添加到此部分。

## 第 3 步：加载包含现有段落的文档

如果要使用包含段落的现有文档，可以使用以下代码加载该文档：

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

此代码加载指定文档（替换“MyDir +”Paragraphs.docx“”使用文档的实际路径）并访问文档第一部分的段落集合。线`Assert.AreEqual(22, paragraphs.Count);`检查文档是否包含 22 个段落。

## 第 4 步：为文档创建一个 DocumentBuilder

您可以使用位置索引将 DocumentBuilder 光标创建到特定段落。

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## 第 5 步：将光标移动到特定段落


您可以使用位置索引将 DocumentBuilder 光标移动到特定段落。方法如下：

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

此代码将 DocumentBuilder 的光标移动到第二部分的第三段（索引为 2 的段落）和位置 10。然后它添加一个包含一些文本的新段落并检查光标是否正确定位在这个新段落上。

### 使用 Aspose.Words for .NET 的 Move To Move To Section 示例源代码

```csharp

	
	Document doc = new Document();
	doc.AppendChild(new Section(doc));

	//将 DocumentBuilder 移动到第二部分并添加文本。
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToSection(1);
	builder.Writeln("Text added to the 2nd section.");

	//创建带段落的文档。
	doc = new Document(MyDir + "Paragraphs.docx");
	ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
	Assert.AreEqual(22, paragraphs.Count);

	//当我们为文档创建一个 DocumentBuilder 时，它的光标默认位于文档的最开头，
	// DocumentBuilder 添加的任何内容都将添加到文档中。
	builder = new DocumentBuilder(doc);
	Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

	//您可以将光标移动到段落中的任何位置。
	builder.MoveToParagraph(2, 10);
	Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
	builder.Writeln("This is a new third paragraph. ");
	Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
	
        
```

就这样 ！您现在已经了解了如何使用提供的源代码使用 Aspose.Words for .NET 的移动到部分功能。您现在可以将此功能集成到您自己的应用程序中，并动态地操作 Word 文档的部分和段落。

