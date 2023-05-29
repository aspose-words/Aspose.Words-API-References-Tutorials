---
title: Table
linktitle: Table
second_title: Aspose.Words for .NET API Reference
description: Learn how to create a table with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/table/
---


In this example, we will walk you through how to create a table using Aspose.Words for .NET. A table is a data structure that organizes information into rows and columns.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Step 2: Add cells and data

We will add cells and data to our table using the `InsertCell` method and the `Writeln` method of the document generator.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Example source code for creating a table with Aspose.Words for .NET

```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Add the first row.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// Add the second row.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

Congratulation ! You have now learned how to create a table with Aspose.Words for .NET.

