---
title: Change Field Update Culture Source
linktitle: Change Field Update Culture Source
second_title: Aspose.Words Document Processing API
description: Change Field Update Culture Source, Step-by-step guide to modify culture source in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/change-field-update-culture-source/
---

In this tutorial, we will guide you through the process of changing the field update culture source in Word documents using Aspose.Words for .NET. By modifying the culture source, you can control the date formatting during field update and mail merge operations. We will provide you with the necessary C# source code and step-by-step instructions to achieve this.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a Document and DocumentBuilder
To start, create an instance of the Document class and a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert Content with Specific Locale
Next, set the locale to German and insert fields with date formatting:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

In the above code, we set the font locale to German (locale ID 1031) and insert two fields with specific date formatting.

## Step 3: Change Field Update Culture Source
To change the field update culture source, use the FieldOptions class:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

In this example, we set the culture used during field update to be chosen from the culture used by the field.

## Step 4: Perform Mail Merge
Perform a mail merge operation and specify the date value for the "Date2" field:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

In this code snippet, we execute the mail merge operation and provide a DateTime value for the "Date2" field.

## Step 5: Save the Document
Save the modified document to a file using the Save method of the Document class:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Example Source Code for Changing Field Update Culture Source using Aspose.Words for .NET
Here is the complete source code for changing the field update culture source in Word documents using Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusion
Congratulations! You have successfully learned how to change the field update culture source in Word documents using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now control the culture used for date formatting during field update and mail merge operations. Customize the culture source according to your requirements to ensure accurate and consistent date.

### FAQ's

#### Q: How can I change the field update culture source in Aspose.Words for .NET?

A: To change the field update culture source in Aspose.Words for .NET, you can use the `Document.FieldOptions.CultureSource` property and set its value to `FieldCultureSource.FieldCode` or `FieldCultureSource.CurrentThread`. For example, you can use `document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` to use the culture defined in the field code.

#### Q: How can I specify a specific culture for updating fields in Aspose.Words for .NET?

A: To specify a specific culture for updating fields in Aspose.Words for .NET, you can use the `Document.FieldOptions.FieldUpdateCultureInfo` property and set the `CultureInfo` object corresponding to the desired culture. For example, you can use `document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` to specify the French (France) culture.

#### Q: Is it possible to disable automatic field updating in Aspose.Words for .NET?

A: Yes, it is possible to disable automatic field updating in Aspose.Words for .NET. You can use the `Document.FieldOptions.UpdateFields` property and set it to `false` to prevent fields from auto-updating. This allows you to manually control the updating of fields as needed.

#### Q: How can I manually update document fields in Aspose.Words for .NET?

A: To manually update fields in a document in Aspose.Words for .NET, you can use the `Field.Update` method for each field individually. For example, you can use `field.Update()` to update the specific field.