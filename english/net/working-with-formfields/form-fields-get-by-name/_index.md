---
title: Form Fields Get By Name
linktitle: Form Fields Get By Name
second_title: Aspose.Words Document Processing API
description: Learn how to retrieve and modify form fields by name in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-formfields/form-fields-get-by-name/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to retrieve form fields by name from a Word document. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by providing the path to your source document containing form fields:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Step 2: Retrieving Form Fields

Next, access the `FormFields` property of the `Range` object in the document to retrieve all the form fields:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

You can retrieve form fields either by index or by name. In this example, we retrieve a form field using both methods:

```csharp
FormField formField1 = documentFormFields[3]; // Retrieving by index
FormField formField2 = documentFormFields["Text2"]; // Retrieving by name
```

## Step 3: Modifying Form Field Properties

Once you have retrieved the form fields, you can modify their properties as needed. In this example, we change the font size of `formField1` to 20 and the font color of `formField2` to red:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Step 4: Saving the Document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

That's it! You have successfully retrieved form fields by name and modified their properties in a Word document using Aspose.Words for .NET.

### Example source code for Form Fields Get By Name using Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Feel free to use this code in your own projects and modify it according to your specific requirements.

### FAQ's

#### Q: How can I get a form field by name in Aspose.Words?

A: To get a form field by name in Aspose.Words, you can use the `Document.Range.FormFields[name]` method. This method returns the form field corresponding to the specified name.

#### Q: What if the form field with the specified name does not exist in the document?

A: If the form field with the specified name does not exist in the document, the `Document.Range.FormFields[name]` method will return `null`. You can check this result to handle cases where the form field is not found.

#### Q: How can I modify the properties of a found form field?

A: Once you get a form field by name, you can access its individual properties to edit them. For example, you can change the field's value, enable or disable its visibility, or modify other properties as needed.

#### Q: Can I get multiple form fields with the same name in a document?

A: Yes, it is possible to have multiple form fields with the same name in a document. In this case, the `Document.Range.FormFields[name]` method will return the first form field found with the specified name. If you have multiple form fields with the same name, you will need to take this into account when manipulating the fields.

#### Q: How can I iterate over all form fields in a document?

A: To iterate over all form fields in a document, you can use a `foreach` loop on the `Document.Range.FormFields` collection. This will allow you to access each form field individually and perform operations on each of them.
