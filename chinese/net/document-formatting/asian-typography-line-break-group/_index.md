---
title: 亚洲版式换行组
linktitle: 亚洲版式换行组
second_title: Aspose.Words 文档处理 API
description: 了解如何将亚洲版式换行符组与 Aspose.Words for .NET 结合使用。
type: docs
weight: 10
url: /zh/net/document-formatting/asian-typography-line-break-group/
---

在本教程中，我们将向您展示如何通过 Aspose.Words for .NET 使用亚洲版式换行组功能。请按照以下步骤了解源代码并应用格式更改。

## 第 1 步：加载文档

首先，指定文档的目录并将包含亚洲版式的文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 第 2 步：亚洲版式设置

我们现在将为文档第一段配置亚洲版式设置。就是这样：

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### 使用 Aspose.Words for .NET 的亚洲版式换行组的示例源代码

以下是 Aspose.Words for .NET 的亚洲版式换行组功能的完整源代码：

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
通过此代码，您将能够使用 Aspose.Words for .NET 应用亚洲版式换行符组。

