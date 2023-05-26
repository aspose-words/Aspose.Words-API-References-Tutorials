---
title: 检测智能艺术形状
linktitle: 检测智能艺术形状
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 检测 Word 文档中的 Smart Art 形状，识别图形表示。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/detect-smart-art-shape/
---

本教程介绍如何使用 Aspose.Words for .NET 检测 Word 文档中的 Smart Art 形状。 Smart Art 形状是用于直观呈现信息和想法的图形表示。

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
使用`Document`构造函数，将文档的路径作为参数传递。

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## 第 3 步：检测智能艺术形状
遍历类型的子节点`Shape`在文档中使用`GetChildNodes`方法。使用`HasSmart Art`财产。

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## 第四步：输出结果
打印在文档中检测到的具有 Smart Art 的形状数。

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### 使用 Aspose.Words for .NET 检测智能艺术形状的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

就是这样！您已使用 Aspose.Words for .NET 成功检测到 Word 文档中的 Smart Art 形状。