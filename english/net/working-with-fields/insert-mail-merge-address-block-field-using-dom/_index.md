---
title: Insert Mail Merge Address Block Field Using DOM
linktitle: Insert Mail Merge Address Block Field Using DOM
second_title: Aspose.Words for .NET API Reference
description: Learn how to Insert a mail merge address block field into your Word documents with Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Insert Mail Merge Address Block Field" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

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

## Step 3: Moving cursor to paragraph

We use the DocumentBuilder's `MoveTo()` method to move the cursor to the paragraph where we want to insert the mail merge address block field.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Step 4: Inserting the Mail Merge Address Block Field

We use the DocumentBuilder's `InsertField()` method to insert a mail merge address block field into the paragraph.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

We then configure the properties of the address block field specifying the appropriate options, such as including country/region name, formatting the address according to country/region, country/region names excluded , name and address format, and language identifier.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

Finally, we call the `Update()` method to update the field.

```csharp
field. Update();
```

### Sample source code for inserting a mail merge address block field with Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// We want to insert a mail merge address block like this:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADDRESSBLOCK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADDRESSBLOCK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```

