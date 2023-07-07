---
title: 应用轮廓边框
linktitle: 应用轮廓边框
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 将轮廓边框应用到表格的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 将轮廓边框应用到表格的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将清楚地了解如何使用 Aspose.Words for .NET 操作 Word 文档中的表格边框。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您的 Word 文档的存储位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第2步：上传文件
接下来，您需要将 Word 文档加载到实例中`Document`班级。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 第 3 步：访问表
要应用轮廓边框，我们需要访问文档中的表格。这`Table`类代表 Aspose.Words 中的一个表。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 步骤 4：将表格与页面中心对齐
现在我们可以使用以下命令将表格与页面中心对齐`Alignment`表的属性。

```csharp
table. Alignment = Table Alignment. Center;
```

## 步骤 5：擦除现有表格边框
要开始新的轮廓边框，我们首先需要从表格中删除所有现有边框。这可以使用以下方法完成`ClearBorders()`方法。

```csharp
table. ClearBorders();
```

## 第 6 步：在表格周围定义绿色边框
我们现在可以使用以下命令在表格周围设置绿色边框`SetBorder()`桌子每一边的方法。在此示例中，我们使用厚度为 1.5 磅、绿色的“单”型边框。

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## 第7步：用背景颜色填充单元格
为了改善表格的视觉呈现，我们可以用底色填充单元格

主意。在此示例中，我们使用浅绿色。

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## 步骤8：保存修改后的文档
最后，我们将修改后的文档保存到文件中。您可以为输出文档选择适当的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

恭喜！现在，您已使用 Aspose.Words for .NET 将轮廓边框应用到表格。

### 使用 Aspose.Words for .NET 应用轮廓边框的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//将表格与页面中心对齐。
	table.Alignment = TableAlignment.Center;
	//清除表格中任何现有的边框。
	table.ClearBorders();
	//在桌子周围设置绿色边框，但不在桌子内部设置绿色边框。
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	//用浅绿色纯色填充单元格。
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将轮廓边框应用到表格。通过遵循此分步指南，您可以轻松地将此功能集成到您的 C# 项目中。操作表格格式是文档处理的一个重要方面，Aspose.Words 提供了强大而灵活的 API 来实现此目的。有了这些知识，您就可以改进 Word 文档的视觉呈现并满足特定要求。