---
title: 亚洲版式换行组
linktitle: 亚洲版式换行组
second_title: Aspose.Words for .NET API 参考
description: 了解如何通过 Aspose.Words for .NET 使用 Asian Typography 换行符组。
type: docs
weight: 10
url: /zh/net/document-formatting/asian-typography-line-break-group/
---

在本教程中，我们将向您展示如何在 Aspose.Words for .NET 中使用 Asian Typography 换行符组功能。按照以下步骤了解源代码并应用格式更改。

## 第 1 步：装入文档

首先，指定文档的目录并将包含亚洲版式的文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 第 2 步：亚洲版式设置

我们现在将为文档的第一段配置亚洲版式设置。就是这样：

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## 第 3 步：保存文档

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### 使用 Aspose.Words for .NET 的亚洲排版换行组示例源代码

以下是 Aspose.Words for .NET 的亚洲字体换行组功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
使用此代码，您将能够使用 Aspose.Words for .NET 应用 Asian Typography 换行符组。

