---
title: 使用特定选项添加文本水印
linktitle: 使用特定选项添加文本水印
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 添加具有特定选项的文本水印。分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

在本教程中，我们将向您介绍如何使用 Aspose.Words for .NET 添加具有特定选项的文本水印。文本水印是叠加在文档上的文本，表示它是草稿、机密等。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：装入文档

我们将使用文档路径加载现有文档。

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 第 3 步：使用特定选项添加文本水印

我们将创建一个实例`TextWatermarkOptions`类并为文本水印设置所需的选项。

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## 第 4 步：保存文档

最后，我们可以保存添加了文本水印的文档。

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### 使用 Aspose.Words for .NET 添加具有特定选项的文本水印的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 使用特定选项添加文本水印。

