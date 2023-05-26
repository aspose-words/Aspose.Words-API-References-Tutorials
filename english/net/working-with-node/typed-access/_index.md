---
title: Typed Access
linktitle: Typed Access
second_title: Aspose.Words for .NET API Reference
description: Learn how to use typed access to manipulate tables in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-node/typed-access/
---

Here is a step by step guide to explain the C# source code below that illustrates how to use the Typed Access feature with Aspose.Words for .NET.

## Step 1: Import the necessary references
Before you begin, make sure you have imported the necessary references to use Aspose.Words for .NET into your project. This includes importing the Aspose.Words library and adding the required namespaces to your source file.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Step 2: Create a new document
In this step, we will create a new document using the `Document` class.

```csharp
Document doc = new Document();
```

## Step 3: Access the section and the body
To access the tables contained in the document, we must first access the section and the body of the document.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## Step 4: Quick and typed access to tables
Now that we have the body of the document, we can use quick and typed access to access all the tables contained in the body.

```csharp
TableCollection tables = body.Tables;
```

## Step 5: Browse tables
By using a `foreach` loop, we can loop through all tables and perform specific operations on each table.

```csharp
foreach(Table table in tables)
{
     // Quick and typed access to the first row of the table.
     table.FirstRow?.Remove();

     // Quick and typed access to the last row of the table.
     table.LastRow?.Remove();
}
```

In this example, we delete the first and last row of each table using the quick and typed access provided by Aspose.Words.

### Sample Source Code for Typed Access with Aspose.Words for .NET

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	// Quick typed access to all Table child nodes contained in the Body.
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		// Quick typed access to the first row of the table.
		table.FirstRow?.Remove();

		// Quick typed access to the last row of the table.
		table.LastRow?.Remove();
	}
            
```

This is a complete sample code for typed access to tables with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.

---

