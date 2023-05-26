---
title: Get Mail Merge Field Names
linktitle: Get Mail Merge Field Names
second_title: Aspose.Words for .NET API Reference
description: Learn how to get mail merge field names in your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/get-mail-merge-field-names/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Get Merge Field Names" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Loading the document

The first step is to load the document where you want to get the merge field names.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Be sure to replace "YOUR DOCUMENT FILE" with the name of your own file.

## Step 3: Get merge field names

We use the `GetFieldNames()` method to get an array containing the names of the merge fields present in the document.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

The `fieldNames` variable now contains the names of the merge fields.

### Source Code Example for Get Merge Field Names with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Get merge field names.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Display the number of merge fields.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

In this example, we loaded a document, got the merge field names using the `GetFieldNames()` method, and displayed the number of merge fields present in the document.

This concludes our guide on using the "Get Merge Field Names" feature with Aspose.Words for .NET.
