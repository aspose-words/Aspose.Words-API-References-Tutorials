---
title: Get Revision Group Details
linktitle: Get Revision Group Details
second_title: Aspose.Words Document Processing API
description: Get revision group details in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/get-revision-group-details/
---

In this step-by-step guide, we are going to show you how to get the details of a group of revisions in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Browse revisions

Next, we'll loop through the revisions present in the document and display their details, such as type, author, date, and revised text.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Example source code for Get Revision Group Details using Aspose.Words for .NET

Here is the complete source code to get the details of a group of revisions in a document using Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Conclusion

In this tutorial, we learned how to get the details of a group of revisions in a Word document using Aspose.Words for .NET. By using a loop and the appropriate properties, we were able to display details such as revision type, author, date, and revised text. Aspose.Words for .NET offers many powerful features for manipulating Word documents, including revision management. You can now use this knowledge to get revision group details into your own Word documents using Aspose.Words for .NET.

### FAQ's

#### Q: How do I load a document with revisions into Aspose.Words for .NET?

A: Use the `Document` class of Aspose.Words for .NET to load a document from a file containing revisions. You can specify the full document path.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: How do I get the details of a revision group in Aspose.Words for .NET?

A: Go through the revisions of the document using a loop and access the properties of each revision to get the details you want. You can use the `RevisionType`, `Author`, `DateTime` and `ParentNode` properties to get the revision type, author, date and revised text respectively.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Q: How to check if a revision belongs to a group in Aspose.Words for .NET?

A: Use the `Group` property of the `Revision` object to check if a revision belongs to a group. If the `Group` property is `null`, it means that the revision does not belong to any group.

```csharp
if (revision.Group != null)
{
      // The revision belongs to a group
}
else
{
      // The revision does not belong to any group
}
```
