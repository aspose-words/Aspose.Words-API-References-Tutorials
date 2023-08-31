---
title: 将边框和底纹应用到 Word 文档中的段落
linktitle: 将边框和底纹应用到 Word 文档中的段落
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将边框和底纹应用到 Word 文档中的段落。
type: docs
weight: 10
url: /zh/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 的功能将边框和底纹应用到 Word 文档中的段落。请按照以下步骤了解源代码并应用格式更改。

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

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 将边框和底纹应用到 Word 文档中的段落。通过配置段落的`Borders`和`Shading`属性中，我们能够设置段落的边框样式、线条颜色和填充颜色。 Aspose.Words for .NET 提供强大的格式化功能来自定义段落的外观并增强文档的视觉表示。

### 常见问题解答

#### 问：如何使用 Aspose.Words for .NET 将边框和底纹应用到 Word 文档中的段落？

答：要使用 Aspose.Words for .NET 将边框和底纹应用到 Word 文档中的段落，请按照下列步骤操作：
1. 创建一个新文档和`DocumentBuilder`目的。
2. 通过访问配置段落边框`Borders`的财产`ParagraphFormat`并设置每边的边框样式。
3. 通过访问配置段落填充`Shading`的财产`ParagraphFormat`并指定纹理和填充颜色。
4. 使用以下命令将内容添加到段落中`Write`的方法`DocumentBuilder`.
5. 使用保存文档`Save`方法。

#### 问：如何设置段落各边的边框样式？

 A：要设置段落各边的边框样式，您可以访问`Borders`的财产`ParagraphFormat`并设置`LineStyle`每个人的财产`BorderType`（例如，`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom`）。您可以指定不同的线条样式，例如`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`， ETC。

#### 问：如何指定段落底纹的纹理和填充颜色？

答：要指定段落底纹的纹理和填充颜色，您可以访问`Shading`的财产`ParagraphFormat`并设置`Texture`属性到所需的纹理索引（例如，`TextureIndex.TextureDiagonalCross` ）。您还可以设置`BackgroundPatternColor`和`ForegroundPatternColor`属性到所需的颜色使用`System.Drawing.Color`班级。