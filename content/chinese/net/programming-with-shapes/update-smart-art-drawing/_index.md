---
title: 更新智能艺术绘图
linktitle: 更新智能艺术绘图
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文档中的 Smart Art 绘图。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/update-smart-art-drawing/
---

本教程介绍如何使用 Aspose.Words for .NET 更新 Word 文档中的 Smart Art 绘图。通过遍历文档中的形状并检查它们是否具有 Smart Art，您可以更新 Smart Art 绘图以反映对其数据所做的任何更改。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载文档
使用`Document`类构造函数。

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## 步骤 3：更新智能艺术绘图
使用`GetChildNodes`方法`NodeType.Shape`参数。使用`HasSmartArt`属性，如果为真，则调用`UpdateSmartArtDrawing`方法来更新 Smart Art 绘图。

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

就是这样！您已成功使用 Aspose.Words for .NET 更新了 Word 文档中的 Smart Art 绘图。