---
title: Update Dirty Fields
linktitle: Update Dirty Fields
second_title: Aspose.Words Document Processing API
description: Learn how to load a Word document by updating dirty fields with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/update-dirty-fields/
---

When working with Word documents in a C# application, it may be necessary to update dirty fields to show the most recent values. With the Aspose.Words library for .NET, you can easily update dirty fields on document load using LoadOptions. In this step-by-step guide, we'll walk you through how to use Aspose.Words for .NET C# source code to load a document by updating dirty fields using LoadOptions.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Configuring Loading Options

The first step is to configure the loading options for our document. Use the LoadOptions class to specify loading parameters. In our case, we need to set the UpdateDirtyFields property to true to update dirty fields. Here's how to do it:

```csharp
LoadOptions loadOptions = new LoadOptions { UpdateDirtyFields = true };
```

We create a new LoadOptions object and set the UpdateDirtyFields property to true to update dirty fields when loading the document.

## Loading document updating dirty fields

Now that we have configured the load options, we can load the document using the Document class and specify the load options. Here is an example :

```csharp
Document doc = new Document(dataDir + "Dirty field.docx", loadOptions);
```

In this example, we load the document "Dirty field.docx" located in the documents directory using the load options specified.

## Example source code for LoadOptions with "Update Dirty Fields" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure loading options with the "Update Dirty Fields" feature
LoadOptions loadOptions = new LoadOptions { UpdateDirtyFields = true };

// Load the document by updating the dirty fields
Document doc = new Document(dataDir + "Dirty field.docx", loadOptions);

// Save the document
doc.Save(dataDir + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

## Conclusion

In this guide, we explained how to upload a document by updating dirty fields using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. The update Dirty fields on document load will display the most recent values in your Word document.

