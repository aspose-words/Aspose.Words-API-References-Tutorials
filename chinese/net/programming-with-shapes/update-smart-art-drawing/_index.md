---
title: 更新智能艺术绘图
linktitle: 更新智能艺术绘图
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文档中的 Smart Art 绘图。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/update-smart-art-drawing/
---

本教程介绍如何使用 Aspose.Words for .NET 更新 Word 文档中的 Smart Art 绘图。通过遍历文档中的形状并检查它们是否具有 Smart Art，您可以更新 Smart Art 绘图以反映对其数据所做的任何更改。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：装入文档
使用`Document`类构造函数。

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## 第 3 步：更新智能艺术绘图
使用`GetChildNodes`方法与`NodeType.Shape`范围。使用`HasSmartArt`属性，如果为真，则调用`UpdateSmartArtDrawing`更新 Smart Art 绘图的方法。

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### 使用 Aspose.Words for .NET 更新智能艺术绘图的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

就是这样！您已经使用 Aspose.Words for .NET 成功更新了 Word 文档中的 Smart Art 绘图。