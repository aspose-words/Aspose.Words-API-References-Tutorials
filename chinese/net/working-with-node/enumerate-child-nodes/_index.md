---
title: 枚举子节点
linktitle: 枚举子节点
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 枚举段落中的子节点。
type: docs
weight: 10
url: /zh/net/working-with-node/enumerate-child-nodes/
---

下面是一个分步指南，用于解释下面的 C# 源代码，该代码说明了如何使用 Aspose.Words for .NET 枚举子节点。

## 第 1 步：导入必要的引用
在您开始之前，请确保您已经导入了必要的引用以将 Aspose.Words for .NET 应用到您的项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到您的源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## 第 2 步：创建新文档
在此步骤中，我们将使用`Document`班级。

```csharp
Document doc = new Document();
```

## 第 3 步：访问段落及其子节点
要枚举段落的子节点，我们首先需要访问段落本身。使用`GetChild`方法与`Paragraph`节点类型获取文档的第一段。

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

接下来，我们使用`ChildNodes`财产。

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## 第四步：浏览子节点
现在我们有了子节点的集合，我们可以使用`foreach`环形。我们检查每个子节点的类型，并根据类型执行特定的操作。

```csharp
foreach (Node child in children)
{
     //一个段落可以包含不同类型的子项，例如连续、形状等。
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

在这个例子中，我们正在检查子节点是否是类型`Run`（例如文本片段）。如果是这样，我们将节点转换为`Run`并使用显示文本`run.Text`.

## 使用 Aspose.Words for .NET 枚举子节点的示例源代码


```csharp
	Document doc = new Document();
	Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

	NodeCollection children = paragraph.ChildNodes;
	foreach (Node child in children)
	{
		//一个段落可能包含各种类型的子项，例如连续、形状等。
		if (child.NodeType == NodeType.Run)
		{
			Run run = (Run) child;
			Console.WriteLine(run.Text);
		}
	}
            
```

这是一个完整的代码示例，用于使用 Aspose.Words for .NET 枚举段落的子节点。确保导入引用

