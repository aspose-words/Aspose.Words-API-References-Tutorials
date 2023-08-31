---
title: Move To Table Cell In Word Document
linktitle: Move To Table Cell In Word Document
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to using Move To Table Cell in word document feature of Aspose.Words for .NET
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-table-cell/
---
In this example, we will walk you through how to use the Move To Table Cell in word document feature of Aspose.Words for .NET using the provided C# source code step by step. This feature allows you to navigate and manipulate specific cells inside a table in a Word document. Follow the steps below to integrate this functionality into your application.

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

## Conclusion

In this example, we explored the Move To Table Cell feature of Aspose.Words for .NET. We learned how to load a document containing a table, move the DocumentBuilder to a specific table cell, and add content to that cell. This feature provides developers with powerful tools to navigate and manipulate specific cells within Word document tables programmatically using Aspose.Words for .NET. It can be a valuable addition to your application for dynamic Word document processing and table content management.

### FAQ's for move to table cell in word document

#### Q: What is the purpose of the Move To Table Cell feature in Aspose.Words for .NET?

A: The Move To Table Cell feature in Aspose.Words for .NET allows developers to navigate to and manipulate specific cells inside a table in a Word document programmatically. It provides the ability to insert, modify, or delete content within a particular cell.

#### Q: How do I move the DocumentBuilder to a specific table cell in a Word document?

A: To move the DocumentBuilder to a specific table cell in a Word document, you can use the MoveToCell method of the DocumentBuilder class. This method takes the indices of the target row and cell within the table as parameters and places the cursor at the beginning of that cell.

#### Q: Can I add or modify content after moving to a specific table cell using the Move To Table Cell feature?

A: Yes, once the DocumentBuilder is positioned at the desired table cell using MoveToCell, you can use various methods of the DocumentBuilder class, such as Write, Writeln, or InsertHtml, to add or modify the content of that cell.

#### Q: How can I verify that the move to the table cell was successful?

A: You can verify the successful move to the table cell by checking the position of the DocumentBuilder's cursor. For example, you can compare the current node of the DocumentBuilder with the cell you intended to move to and verify that the content added by the DocumentBuilder is correctly saved in the table cell.
