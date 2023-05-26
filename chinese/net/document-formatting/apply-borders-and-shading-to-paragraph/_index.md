---
title: 对段落应用边框和底纹
linktitle: 对段落应用边框和底纹
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将边框和底纹应用于段落。
type: docs
weight: 10
url: /zh/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 的功能将边框和底纹应用于段落。按照以下步骤了解源代码并应用格式更改。

## 第 1 步：创建和配置文档

首先，创建一个新文档和一个关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第二步：边框配置

现在让我们通过指定每一边的边框样式来配置段落边框。就是这样：

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## 第 3 步：填充设置

我们现在将通过指定纹理和填充颜色来配置段落填充。就是这样：

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## 第 4 步：添加内容

我们将在段落中添加一些格式化的内容。就是这样：

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## 第 3 步：保存文档

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### 使用 Aspose.Words for .NET 将边框和底纹应用于段落的示例源代码

以下是使用 Aspose.Words for .NET 将边框和底纹应用到段落功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```
