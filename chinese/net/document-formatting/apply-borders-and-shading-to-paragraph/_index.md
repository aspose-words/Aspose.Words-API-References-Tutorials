---
title: 将边框和底纹应用于段落
linktitle: 将边框和底纹应用于段落
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将边框和底纹应用到段落。
type: docs
weight: 10
url: /zh/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 的功能将边框和底纹应用到段落。请按照以下步骤了解源代码并应用格式更改。

## 第 1 步：创建并配置文档

首先，创建一个新文档和关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第2步：边框配置

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

我们将向该段落添加一些格式化内容。就是这样：

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### 使用 Aspose.Words for .NET 将边框和底纹应用到段落的示例源代码

以下是 Aspose.Words for .NET 的“将边框和阴影应用于段落”功能的完整源代码：

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
