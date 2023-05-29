---
title: Insert Check Box Form Field
linktitle: Insert Check Box Form Field
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert check box form fields in Word documents using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-check-box-form-field/
---

In this comprehensive tutorial, you will learn how to insert a check box form field into a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to add check box form fields with customizable properties to your documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert a Check Box Form Field
Next, use the InsertCheckBox method of the DocumentBuilder class to insert a check box form field. Provide the name, checked state, default state, and size parameters as arguments:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Step 3: Save the Document
After inserting the check box form field, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Example Source Code for Insert Check Box Form Field using Aspose.Words for .NET
Here is the complete source code for inserting a check box form field using Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

Remember to adjust the code according to your specific requirements and enhance it with additional functionality as needed.

## Conclusion
Congratulations! You have successfully learned how to insert a check box form field into a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now enhance your documents with interactive check box form fields.

