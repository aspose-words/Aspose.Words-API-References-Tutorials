---
title: 移动到表格单元格
linktitle: 移动到表格单元格
second_title: Aspose.Words for .NET API 参考
description: 在 Aspose.Words for .NET 中使用移动到表格单元格的分步指南
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/move-to-table-cell/
---

在本例中，我们将逐步指导您使用提供的 C# 源代码如何使用 Aspose.Words for .NET 的移动到表格单元格功能。此功能允许您在 Word 文档中导航和操作表格内的特定单元格。按照以下步骤将此功能集成到您的应用程序中。

## 第 1 步：加载包含表格的文档

首先，我们需要加载包含要将单元格移动到其中的表格的文档。使用以下代码完成此步骤：

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

此代码加载指定文档（替换“MyDir +”Tables.docx“”使用包含表格的文档的实际路径）。

## 第 2 步：将 DocumentBuilder 移动到特定的表格单元格

接下来，我们会将 DocumentBuilder 移动到特定的表格单元格。使用以下代码执行此步骤：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

此代码从现有文档创建一个 DocumentBuilder，然后将光标从 DocumentBuilder 移动到指定的表格单元格。最后，它使用 DocumentBuilder 的`Write()`方法。

## 第 3 步：检查结果

您现在可以验证移动到表格单元格是否成功。使用以下代码完成此步骤：

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

此代码验证指定的单元格确实是 DocumentBuilder 的当前单元格。它还验证 DocumentBuilder 添加的内容是否已正确保存在表格单元格中。

就这样 ！您现在已经了解了如何使用提供的源代码使用 Aspose.Words for .NET 的移动到表格单元格功能。您现在可以将此功能集成到您自己的应用程序中，并在 Word 文档中操作特定的表格单元格。


### 使用 Aspose.Words for .NET 移动到表格单元格的示例源代码


```csharp

	Document doc = new Document(MyDir + "Tables.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	//将构建器移至第一个表格的第 3 行第 4 单元格。
	builder.MoveToCell(0, 2, 3, 0);
	builder.Write("\nCell contents added by DocumentBuilder");
	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
	Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());

```
