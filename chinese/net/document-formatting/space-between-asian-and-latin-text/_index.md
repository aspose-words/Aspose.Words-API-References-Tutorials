---
title: 亚洲文本和拉丁文本之间的空间
linktitle: 亚洲文本和拉丁文本之间的空间
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 自动调整文档中亚洲文本和拉丁文本之间的间距。
type: docs
weight: 10
url: /zh/net/document-formatting/space-between-asian-and-latin-text/
---

在本教程中，我们将向您展示如何在 Aspose.Words for .NET 中使用亚洲和拉丁文本之间的空格功能。按照以下步骤了解源代码并应用更改。

## 第 1 步：创建和配置文档

首先，创建一个新文档和一个关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：设置亚洲文本和拉丁文本之间的间距

我们现在将使用 ParagraphFormat 对象的属性配置亚洲和拉丁文本之间的空间。就是这样：

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## 第 3 步：保存文档

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### 使用 Aspose.Words for .NET 的亚洲文本和拉丁文本之间的间距示例源代码

以下是 Aspose.Words for .NET 的亚洲文本和拉丁文本之间的空格功能的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

使用此代码，您将能够使用 Aspose.Words for .NET 自动调整文档中亚洲文本和拉丁文本之间的间距。



