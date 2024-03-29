---
title: Update Bookmark Data In Word Document
linktitle: Update Bookmark Data
second_title: Aspose.Words Document Processing API
description: Step by step guide to explain the C# source code of Aspose.Words bookmark data update in word document feature for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/update-bookmark-data/
---

In this tutorial, we will walk through a step-by-step guide to understand and implement the Update Bookmark Data in word document feature of Aspose.Words for .NET. This feature allows you to update the content and properties of bookmarks within a Word document using C# source code.

## Requirements

Before proceeding with the tutorial, make sure you have the following requirements in place:

- Aspose.Words for .NET library installed
- Basic knowledge of C# programming language
- Visual Studio or any other compatible IDE

## Step 1: Load the document

In this step, we will load the Word document that contains the bookmarks we want to update. Assuming you have the document stored in a specific directory, use the following code to load the document:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual directory path where your document is located.

## Step 2: Access the bookmark

To update the bookmark data, we first need to access the specific bookmark within the document. Each bookmark has a unique name associated with it. Use the following code to access a bookmark named "MyBookmark1":

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

Make sure the bookmark name matches the one in your document. You can modify it as per your requirement.

## Step 3: Update bookmark properties and content

Once you have accessed the bookmark, you can update its properties and content. In the following code snippet, we will update the bookmark name and text:

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

You can customize the bookmark name and the new text according to your needs. The above code renames the bookmark to "RenamedBookmark" and updates the text content.

## Step 4: Save the updated document

After updating the bookmark data, you need to save the modified document. Use the following code to save the document:

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

This code will save the modified document with the name "UpdatedDocument.docx" in the same directory as the original document.

### Example source code for Update Bookmark Data using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual directory path where your document is located.

## Conclusion

Congratulations! You have successfully learned how to update bookmark data using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you should now be able to incorporate this feature into your C# applications and manipulate bookmarks within Word documents programmatically.

### FAQ's for update bookmark data in word document

#### Q: Does the update bookmark data feature only work with bookmarks in Word documents?

A: Yes, the Update Bookmark Data feature is specifically designed for bookmarks in Word documents. It lets you update the content and properties of bookmarks in a Word document.

#### Q: Can I update other bookmark properties besides text?

A: Yes, in addition to text, you can also update other bookmark properties, such as bookmark name, bookmark scope, etc. Use the appropriate properties of the `Bookmark` object to update the desired properties.

#### Q: Can I update multiple bookmarks in the same document?

A: Yes, you can update multiple bookmarks in the same document by repeating the access and update steps for each bookmark. Be sure to use unique bookmark names for each bookmark you want to update.

#### Q: Does the update bookmark data function modify the original document?

A: Yes, the bookmark data update feature modifies the original document by updating bookmark properties and content. Be sure to save a copy of the original document before applying this feature.
