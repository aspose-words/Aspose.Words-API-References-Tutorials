---
title: Form Fields Get Form Fields Collection
linktitle: Form Fields Get Form Fields Collection
second_title: Aspose.Words for .NET API Reference
description: Learn how to retrieve and manipulate form fields collection in Word documents using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-formfields/form-fields-get-form-fields-collection/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to retrieve the collection of form fields from a Word document. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by providing the path to your source document containing form fields:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## Step 2: Retrieving the Form Fields Collection

Next, access the `FormFields` property of the `Range` object in the document to retrieve the collection of form fields:

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

Now, you have the collection of form fields from the Word document stored in the `formFields` variable.

## Step 3: Accessing and Manipulating the Form Fields

You can iterate through the form fields collection and perform various operations on each form field, such as getting or setting values, modifying formatting, or extracting information.

```csharp
foreach (FormField formField in formFields)
{
    // Access and manipulate each form field
    // ...
}
```

## Step 4: Saving the Document

Finally, save the modified document if necessary:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

That's it! You have successfully retrieved the collection of form fields from a Word document using Aspose.Words for .NET.

### Example source code for Form Fields Get Form Fields Collection using Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// Access and manipulate the form fields as needed
// ...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Feel free to use this code in your own projects and modify it according to your specific requirements.