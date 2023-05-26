---
title: Insert Nested Fields
linktitle: Insert Nested Fields
second_title: Aspose.Words for .NET API Reference
description: Learn how to easily insert nested fields into your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-nested-fields/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Insert Nested Fields" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the Document and DocumentBuilder

We start by creating a new document and initializing a DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Inserting page breaks

We use a loop to insert multiple page breaks into the document.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Step 4: Move to Footer

We use the `MoveToHeaderFooter()` method of the DocumentBuilder to move the cursor to the main footer.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Step 5: Inserting the nested field

We use the DocumentBuilder's `InsertField()` method to insert a nested field into the footer.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

Finally, we call the `Update()` method to update the field.

```csharp
field. Update();
```

### Sample source code for inserting nested fields with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and the DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert page breaks.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Move to footer.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Insert nested field.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Update the field.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

In this example, we created a new document, inserted page breaks, moved the cursor to the footer, and then inserted a nested field in the footer.