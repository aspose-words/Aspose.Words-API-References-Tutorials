---
title: 单元格布局
linktitle: 单元格布局
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档的表格单元格内布置形状。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/layout-in-cell/
---

本教程解释了如何使用 Aspose.Words for .NET 在 Word 文档的表格单元格内布置形状。通过调整形状属性和使用布局选项，您可以控制单元格中形状的定位和外观。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：构建表格
使用`StartTable`, `EndTable`, `InsertCell`， 和`Write`的方法`DocumentBuilder`对象建表。使用设置所需的行高和高度规则`RowFormat`特性。

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## 第 4 步：创建形状并设置形状格式
创建一个`Shape`对象并配置其属性以定义水印。使用`IsLayoutInCell`财产。

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## 第 5 步：自定义形状
通过设置属性来自定义水印形状的外观和文本，例如`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`， ETC。

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## 第 6 步：将形状插入文档
使用`InsertNode`的方法`DocumentBuilder`目的。使用定位形状`MoveTo`方法将其放置在文档中最后一次运行之后。

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## 第 7 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在此示例中，我们将文档保存为“WorkingWithShapes.LayoutInCell.docx”。

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### 使用 Aspose.Words for .NET 在单元格中布局的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, //如果要将形状放入单元格，则在表格单元格外显示形状。
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地在 Word 文档的表格单元格内布置了一个形状。