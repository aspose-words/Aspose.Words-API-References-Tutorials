---
title: Move To Table Cell
linktitle: Move To Table Cell
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to using Move To Table Cell in Aspose.Words for .NET
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-table-cell/
---

In this example, we will walk you through how to use the Move To Table Cell feature of Aspose.Words for .NET using the provided C# source code step by step. This feature allows you to navigate and manipulate specific cells inside a table in a Word document. Follow the steps below to integrate this functionality into your application.

## Step 1: Load the document containing the table

First, we need to load the document containing the table into which we want to move the cell. Use the following code to accomplish this step:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

This code loads the specified document (replace "MyDir + "Tables.docx"" with the actual path of your document containing the table).

## Step 2: Move the DocumentBuilder to a specific table cell

Next, we'll move the DocumentBuilder to a specific table cell. Use the following code to perform this step:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

This code creates a DocumentBuilder from the existing document and then moves the cursor from the DocumentBuilder to the specified table cell. Finally, it adds content to that cell using the DocumentBuilder's `Write()` method.

## Step 3: Check the result

You can now verify that the move to the table cell was successful. Use the following code to accomplish this step:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

This code verifies that the specified cell is indeed the current cell of the DocumentBuilder. It also verifies that the content added by the DocumentBuilder has been correctly saved in the table cell.

That's all ! You have now understood how to use the move to table cell functionality of Aspose.Words for .NET using the provided source code. You can now integrate this functionality into your own application and manipulate specific table cells in Word documents.


### Example source code for moving to a table cell using Aspose.Words for .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Move the builder to row 3, cell 4 of the first table.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

