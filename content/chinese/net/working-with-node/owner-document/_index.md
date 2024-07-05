---
title: 业主文件
linktitle: 业主文件
second_title: Aspose.Words 文档处理 API
description: 了解如何在 Aspose.Words for .NET 中使用所有者文档。
type: docs
weight: 10
url: /zh/net/working-with-node/owner-document/
---

下面是逐步指南，解释下面的 C# 源代码，说明如何使用 Aspose.Words for .NET 的专有文档功能。

## 步骤 1：导入必要的参考资料
开始之前，请确保已将使用 Aspose.Words for .NET 所需的引用导入到项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## 步骤 2：创建新文档
在此步骤中，我们将使用`Document`班级。

```csharp
Document doc = new Document();
```

## 步骤 3：创建包含所有者文档的节点
创建任何类型的新节点时，都必须将文档传递给构造函数。在此示例中，我们使用文档创建一个新的段落节点`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## 步骤 4：检查父节点和所有者文档
现在我们已经创建了段落节点，我们可以检查它是否有父节点，以及所属文档是否与`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## 步骤 5：使用文档数据修改节点属性
节点与文档之间的关系允许访问和修改引用文档特定数据（例如样式或列表）的属性。在此示例中，我们将段落样式名称设置为“标题 1”。

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## 步骤 6：将段落添加到文档
现在我们可以将段落节点添加到文档的主要部分。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 步骤 7：添加后验证父节点
将段落添加到文档后，我们再次检查它现在是否有父节点。

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### 使用 Aspose.Words for .NET 的所有者文档示例源代码

```csharp
Document doc = new Document();

//创建任何类型的新节点都需要将文档传递到构造函数中。
Paragraph para = new Paragraph(doc);

//新的段落节点尚无父节点。
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

//但是段落节点知道它的文档。
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

//由于节点始终属于某个文档，因此我们能够访问和修改
//引用文档范围数据（例如样式或列表）的属性。
para.ParagraphFormat.StyleName = "Heading 1";

//现在将该段落添加到第一部分的正文中。
doc.FirstSection.Body.AppendChild(para);

//段落节点现在是 Body 节点的子节点。
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```

### 常见问题解答

#### 问：Node.js 中的专有文档是什么？

答：Node.js 中的所有者文档是特定节点所属的 XML 文档。它表示包含该节点的 XML 文档的实例。

#### 问：如何获取节点的所有者文档？

答：要获取 Node.js 中节点的所有者文档，您可以使用`ownerDocument`节点的属性。此属性返回拥有该节点的 XML 文档。

#### 问：专有文档有何用途？

答：所有者文档用于表示 XML 文档中节点的全局上下文。它提供对文档中其他节点的访问，并允许对其执行操作。

#### 问：我们可以修改节点的所有者文档吗？

答：大多数情况下，节点的文档所有者在创建节点时就已确定，无法直接更改。所有者文档是只读属性。

#### 问：如何访问所有者文档的节点？

答：要访问专有文档中的节点，您可以使用 Node.js 环境中使用的 XML API 提供的方法和属性。例如，您可以使用以下方法`getElementsByTagName`或者`querySelector`选择文档中的特定节点。