---
title: Set Table Title And Description
linktitle: Set Table Title And Description
second_title: Aspose.Words Document Processing API
description: Step by step guide to set title and description of a table using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/set-table-title-and-description/
---

In this tutorial, we'll walk you through the step-by-step process to set a table's title and description using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to add a title and description to a table in your Word documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited Word document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document containing the table
Next, you need to load the document containing the table using the `Document` class. Be sure to specify the correct document path.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Step 3: Access the table and set the title and description
Now you can access the table in the document using the `GetChild()` method and the `Table` class. Next, set the table title and description using the `Title` and `Description` properties.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table.Title = "Test Title";
table.Description = "Test Description";
```

## Step 4: Set backup options
If you want to specify save options, you can configure them using the `OoxmlSaveOptions` class. In this example, we have used the `Compliance` option to specify compliance with the ISO 29500:2008 Strict format.

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };
```

## Step 5: Optimize document compatibility
You can also optimize document compatibility using the `OptimizeFor()` method of the `CompatibilityOptions` class. In this example, we've optimized the document for Word 2016.

```csharp
doc.CompatibilityOptions.OptimizeFor(Aspose.Words.Settings.MsWordVersion.Word2016);
```

## Step 6: Save the modified document
Finally, you can save the modified document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.



```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetTableTitleAndDescription.docx", options);
```

### Sample source code for Set Table Title And Description using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.Title = "Test title";
	table.Description = "Test description";
	OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };
	doc.CompatibilityOptions.OptimizeFor(Aspose.Words.Settings.MsWordVersion.Word2016);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetTableTitleAndDescription.docx", options);
```

## Conclusion
In this tutorial, we learned how to set a table's title and description using Aspose.Words for .NET. By following this step-by-step guide, you can easily add a title and description to a table in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can customize the structure and information associated with your tables to your specific needs.
