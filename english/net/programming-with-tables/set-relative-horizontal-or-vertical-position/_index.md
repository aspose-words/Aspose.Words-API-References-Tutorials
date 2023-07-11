---
title: Set Relative Horizontal Or Vertical Position
linktitle: Set Relative Horizontal Or Vertical Position
second_title: Aspose.Words Document Processing API
description: Learn how to set the relative horizontal or vertical position of a table in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

In this tutorial, we are going to learn how to set the relative horizontal or vertical position of a table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to set the relative horizontal or vertical position of your table in your Word documents.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document
To start working with the document, follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory and provide the correct file name.

## Step 3: Setting the relative position of the table
Next, we'll set the relative horizontal or vertical position of the table. Use the following code:

```csharp
// Retrieve the table
Table table = doc.FirstSection.Body.Tables[0];

// Definition of the relative horizontal position of the table
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Define the relative vertical position of the table
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

Here we use the document to retrieve the first table from the body of the first section. Next, we set the relative horizontal position of the table with the `HorizontalAnchor` property using the `RelativeHorizontalPosition.Column` value. Similarly, we set the relative vertical position of the table with the `VerticalAnchor` property using the `RelativeVerticalPosition.Page` value.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the relative position of the table defined. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Set Relative Horizontal Or Vertical Position using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Conclusion
In this tutorial, we learned how to set the relative horizontal or vertical position of a table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can apply this relative position to your tables in your Word documents.
