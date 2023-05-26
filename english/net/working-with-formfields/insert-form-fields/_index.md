---
title: Insert Form Fields
linktitle: Insert Form Fields
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert dropdown form fields into Word documents using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-formfields/insert-form-fields/
---

In this step-by-step tutorial, we will guide you on how to insert form fields, specifically a dropdown form field, into a Word document using Aspose.Words for .NET. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document and DocumentBuilder Objects

First, initialize the `Document` and `DocumentBuilder` objects:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Inserting a Dropdown Form Field

Next, specify the options for the dropdown form field and insert it into the document using the `InsertComboBox` method of the `DocumentBuilder` object. In this example, we insert a dropdown form field named "DropDown" with three options: "One," "Two," and "Three":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Step 3: Saving the Document

Finally, save the document:

```csharp
doc.Save("OutputDocument.docx");
```

That's it! You have successfully inserted a dropdown form field into a Word document using Aspose.Words for .NET.

### Example source code for Insert Form Fields using Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Feel free to use this code in your own projects and modify it according to your specific requirements.