---
title: Replace Hyperlinks
linktitle: Replace Hyperlinks
second_title: Aspose.Words for .NET API Reference
description: Replace hyperlinks in Word documents using Aspose.Words for .NET. Step-by-step instructions for replacing hyperlinks.
type: docs
weight: 10
url: /net/working-with-fields/replace-hyperlinks/
---

Here is a step-by-step guide to explain the following C# source code to replace hyperlinks using Aspose.Words for .NET functionality. Make sure you have included the Aspose.Words library in your project before using this code.

## Step 1: Set document directory path

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Be sure to specify the correct path to your documents directory containing the `Hyperlinks.docx` file.

## Step 2: Load the document containing the hyperlinks

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Here we are creating an instance of the `Document` class from the specified file.

## Step 3: Browse fields to find hyperlinks

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Some hyperlinks may be local (links to bookmarks inside the document), we ignore them.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

This loop goes through all fields in the document looking for fields of type `FieldType.FieldHyperlink`. Once a field of this type is found, we check if it is a local link by checking the `SubAddress` property. If not, we replace the link address with `"http://www.aspose.com"` and the result with `"Aspose - The .NET & Java Component Editor"`.

## Step 4: Save the modified document

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Finally, we save the modified document with the replaced hyperlinks to a specified file.

### Example source code to replace hyperlinks with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Some hyperlinks may be local (links to bookmarks inside the document), we ignore them.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

This is sample source code to replace hyperlinks in a document using Aspose.Words for .NET.

### FAQ's

#### Q: How can I replace hyperlinks in a Word document using Aspose.Words for .NET?

A: To replace hyperlinks in a Word document using Aspose.Words for .NET, you can use the `Document.Range.Replace` method specifying the text to search for and the replacement text. Be sure to use the appropriate options to set search and replace parameters.

#### Q: Is it possible to replace only certain hyperlinks in a Word document with Aspose.Words for .NET?

A: Yes, it is possible to replace only certain hyperlinks in a Word document with Aspose.Words for .NET. You can filter the hyperlinks to be replaced using specific criteria, such as link URL, link text, or any other relevant property. Then you can apply the replacement only to the matching hyperlinks.

#### Q: How can I ignore hyperlinks in headers, footers or footnotes when replacing with Aspose.Words for .NET?

A: To ignore hyperlinks in headers, footers, or footnotes when replacing with Aspose.Words for .NET, you can use the advanced search options and specify appropriate search limits. For example, you can limit the search to major sections of the document and exclude headers, footers, or footnotes.

#### Q: Is it possible to replace hyperlinks with internal links to other parts of the document?

A: Yes, it is possible to replace hyperlinks with internal links to other parts of the document with Aspose.Words for .NET. You can use anchors or text ids to create internal links and then replace them using the `Document.Range.Replace` method with the appropriate options.

#### Q: Does replacing hyperlinks with Aspose.Words for .NET preserve link properties, such as colors or styles?

A: Yes, when replacing hyperlinks with Aspose.Words for .NET, link properties such as colors or styles are retained. You can specify the same formatting properties in the replacement text to achieve a consistent result.
