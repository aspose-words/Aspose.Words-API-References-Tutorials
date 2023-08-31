---
title: 移至 Word 文档中的表格单元格
linktitle: 移至 Word 文档中的表格单元格
second_title: Aspose.Words 文档处理 API
description: 在 Aspose.Words for .NET 的 Word 文档功能中使用“移动到表格单元格”的分步指南
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/move-to-table-cell/
---
在此示例中，我们将逐步引导您使用提供的 C# 源代码来使用 Aspose.Words for .NET 的 Word 文档中的移动到表格单元格功能。此功能允许您导航和操作 Word 文档表格内的特定单元格。请按照以下步骤将此功能集成到您的应用程序中。

## 第 1 步：加载包含表格的文档

首先，我们需要加载包含要将单元格移入其中的表格的文档。使用以下代码完成此步骤：

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

此代码加载指定文档（替换“MyDir +”Tables.docx””与包含该表的文档的实际路径）。

## 步骤 2：将 DocumentBuilder 移动到特定的表格单元格

接下来，我们将 DocumentBuilder 移动到特定的表格单元格。使用以下代码来执行此步骤：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

此代码从现有文档创建一个 DocumentBuilder，然后将光标从 DocumentBuilder 移动到指定的表格单元格。最后，它使用 DocumentBuilder 向该单元格添加内容`Write()`方法。

## 第 3 步：检查结果

您现在可以验证是否已成功移动到表格单元格。使用以下代码完成此步骤：

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

此代码验证指定的单元格确实是 DocumentBuilder 的当前单元格。它还验证 DocumentBuilder 添加的内容是否已正确保存在表格单元格中。

就这样 ！您现在已经了解了如何使用提供的源代码来使用 Aspose.Words for .NET 的移动到表格单元格功能。您现在可以将此功能集成到您自己的应用程序中并操作 Word 文档中的特定表格单元格。


### 使用 Aspose.Words for .NET 移动到表格单元格的示例源代码


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

//将构建器移至第一个表的第 3 行、单元格 4。
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## 结论

在此示例中，我们探索了 Aspose.Words for .NET 的“移至表格单元格”功能。我们学习了如何加载包含表格的文档、将 DocumentBuilder 移动到特定的表格单元格以及向该单元格添加内容。此功能为开发人员提供了强大的工具，可以使用 Aspose.Words for .NET 以编程方式导航和操作 Word 文档表格中的特定单元格。它可以为您的动态 Word 文档处理和表格内容管理应用程序提供有价值的补充。

### Word 文档中移动到表格单元格的常见问题解答

#### 问：Aspose.Words for .NET 中“移至表格单元格”功能的用途是什么？

答：Aspose.Words for .NET 中的“移动到表格单元格”功能允许开发人员以编程方式导航到并操作 Word 文档表格内的特定单元格。它提供了在特定单元格内插入、修改或删除内容的能力。

#### 问：如何将 DocumentBuilder 移动到 Word 文档中的特定表格单元格？

答：要将 DocumentBuilder 移动到 Word 文档中的特定表格单元格，可以使用 DocumentBuilder 类的 MoveToCell 方法。此方法将表中目标行和单元格的索引作为参数，并将光标置于该单元格的开头。

#### 问：使用“移至表格单元格”功能移至特定表格单元格后，我可以添加或修改内容吗？

答：是的，一旦使用 MoveToCell 将 DocumentBuilder 定位到所需的表格单元格，您就可以使用 DocumentBuilder 类的各种方法（例如 Write、Writeln 或 InsertHtml）来添加或修改该单元格的内容。

#### 问：如何验证移动到表格单元格是否成功？

答：您可以通过检查 DocumentBuilder 光标的位置来验证是否成功移动到表格单元格。例如，您可以将 DocumentBuilder 的当前节点与要移动到的单元格进行比较，并验证 DocumentBuilder 添加的内容是否正确保存在表格单元格中。