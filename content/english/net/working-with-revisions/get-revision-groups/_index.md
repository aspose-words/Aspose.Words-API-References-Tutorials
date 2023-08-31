---
title: Get Revision Groups
linktitle: Get Revision Groups
second_title: Aspose.Words Document Processing API
description: Get revision groups in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/get-revision-groups/
---

In this step by step guide, we are going to tell you how to get the revision groups in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Browse Revision Groups

Next, we will loop through the revision groups present in the document and display their details, such as author, revision type, and revised text.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Example source code for Get Revision Groups using Aspose.Words for .NET

Here is the complete source code to get the revision groups in a document using Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Conclusion

In this tutorial, we learned how to get the revision groups in a Word document using Aspose.Words for .NET. We followed the steps to load the document and browse the review groups, displaying details such as author and review type. You can now apply this knowledge to analyze revisions of your own Word document using Aspose.Words for .NET.

### FAQ's

#### Q: How to upload a document in Aspose.Words for .NET?

A: Use the `Document` class of Aspose.Words for .NET to load a document from a file. You can specify the full document path.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: How to browse revision groups in a document in Aspose.Words for .NET?

A: Use the `Groups` property of the document `Revisions` object to get the collection of revision groups. You can then use a loop to loop through each review group.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Process each review group here
}
```

#### Q: How to get the author of a review group in Aspose.Words for .NET?

A: Use the `Author` property of the `RevisionGroup` object to get the author of the revision group.

```csharp
string author = group.Author;
```

#### Q: How to get the revision type of a revision group in Aspose.Words for .NET?

A: Use the `RevisionType` property of the `RevisionGroup` object to get the revision type of the group.

```csharp
string revisionType = group.RevisionType;
```
