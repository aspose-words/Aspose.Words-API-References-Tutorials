---
title: 对齐网格
linktitle: 对齐网格
second_title: Aspose.Words for .NET API 参考
description: 分步指南解释使用 Aspose.Words for .NET 实现对齐网格功能的 C# 源代码。
type: docs
weight: 10
url: /zh/net/document-formatting/snap-to-grid/
---

在本教程中，我们将引导您了解如何将“对齐网格”功能与 Aspose.Words for .NET 结合使用。请按照以下步骤了解源代码并应用更改。

## 第 1 步：创建并配置文档

首先，创建一个新文档和关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：网格对齐

现在我们将对特定段落以及该段落中使用的字体应用网格对齐。就是这样：

```csharp
//启用段落网格对齐
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

//在段落中写下文字
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

//为段落中使用的字体启用网格对齐
par.Runs[0].Font.SnapToGrid = true;
```

## 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### 使用 Aspose.Words for .NET 对齐网格的示例源代码

以下是 Aspose.Words for .NET 的“对齐网格”功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//优化输入亚洲字符时的布局。
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

通过此代码，您将能够使用 Aspose.Words for .NET 将文本与网格对齐并优化文档的外观。

