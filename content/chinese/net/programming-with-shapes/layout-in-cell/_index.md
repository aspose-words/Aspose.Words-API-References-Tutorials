---
title: 单元格布局
linktitle: 单元格布局
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档的表格单元格内布局形状。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/layout-in-cell/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档的表格单元格内布局形状。通过调整形状属性并使用布局选项，您可以控制单元格内形状的位置和外观。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理该文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：构建表格
使用`StartTable`, `EndTable`, `InsertCell`， 和`Write`方法`DocumentBuilder`对象来构建表格。使用`RowFormat`特性。

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

## 步骤 4：创建并格式化形状
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

## 步骤 5：自定义形状
通过设置以下属性来自定义水印形状的外观和文本`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`， ETC。

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## 步骤 6：将形状插入文档
使用`InsertNode`方法`DocumentBuilder`对象。使用`MoveTo`方法将其放置在文档中的最后一次运行之后。

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## 步骤 7：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithShapes.LayoutInCell.docx”。

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### 使用 Aspose.Words for .NET 进行单元格布局的示例源代码 

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
		IsLayoutInCell = true, //如果要将其放入单元格中，则在表格单元格外部显示该形状。
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

就是这样！您已成功使用 Aspose.Words for .NET 在 Word 文档的表格单元格内布局形状。