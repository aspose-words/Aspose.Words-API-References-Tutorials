---
title: Delete Fields
linktitle: Delete Fields
second_title: Aspose.Words for .NET API Reference
description: Step by step guide for deleting merge fields in your Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/delete-fields/
---

To explain how to use the "Delete Fields" feature in Aspose. Words for .NET we've created a step by step guide below. 

Its important to follow each step closely in order to achieve the desired results. 

## Step 1: Creating a New Document

In this code snippet we start by creating a new empty document using the following line: 

```csharp
Document doc = new Document();
```

## Step 2: Remove Merge Fields

To remove all merge fields present in the document we use the `DeleteFields()` function. 

This is particularly useful if you wish to keep only the static content and remove any merge information. 

### Source Code Example for Delete Fields with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load existing document.
Document doc = new Document(dataDir + "YourDocument.docx");

// Remove merge fields.
doc.MailMerge.DeleteFields();

// Save the modified document.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

In our example we first load an existing document before calling `DeleteFields()`. Finally we save the modified document with a new filename. 

In order to effectively remove merge fields from a document using Aspose.Words for .NET's "Remove Fields" feature, take a cue from this example. 

Always remember to replace "YOUR DOCUMENTS DIRECTORY" with your specific directory path. 

Our guide on implementing the "Delete Fields" functionality through Aspose.Words for .NET has thus been concluded.