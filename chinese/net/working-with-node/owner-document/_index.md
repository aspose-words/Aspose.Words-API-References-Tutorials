---
title: 业主文件
linktitle: 业主文件
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中使用所有者文档。
type: docs
weight: 10
url: /zh/net/working-with-node/owner-document/
---

这是一个分步指南，用于解释下面的 C# 源代码，说明如何使用 Aspose.Words for .NET 的专有文档功能。

## 第 1 步：导入必要的引用
在您开始之前，请确保您已经导入了必要的引用以将 Aspose.Words for .NET 应用到您的项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到您的源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## 第 2 步：创建新文档
在此步骤中，我们将使用`Document`班级。

```csharp
Document doc = new Document();
```

## 第 3 步：使用所有者文档创建节点
当您创建任何类型的新节点时，您必须将文档传递给构造函数。在此示例中，我们使用文档创建一个新的段落节点`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## 第 4 步：检查父节点和所有者文档
现在我们已经创建了段落节点，我们可以检查它是否有父节点以及拥有文档是否与`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## 第 5 步：使用文档数据修改节点属性
节点和文档之间的关系允许访问和修改引用特定于文档的数据（例如样式或列表）的属性。在此示例中，我们将段落样式名称设置为“标题 1”。

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## 第 6 步：将段落添加到文档中
现在我们可以将段落节点添加到文档的主要部分。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 第七步：添加后验证父节点
将段落添加到文档后，我们再次检查它现在是否有父节点。

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### 使用 Aspose.Words for .NET 的所有者文档示例源代码

```csharp
Document doc = new Document();

//创建任何类型的新节点都需要将文档传递给构造函数。
Paragraph para = new Paragraph(doc);

//新的段落节点还没有父节点。
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

//但是段落节点知道它的文档。
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

//一个节点总是属于一个文档的事实允许我们访问和修改
//引用文档范围数据的属性，例如样式或列表。
para.ParagraphFormat.StyleName = "Heading 1";

//现在将段落添加到第一节的正文中。
doc.FirstSection.Body.AppendChild(para);

//段落节点现在是 Body 节点的子节点。
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```



