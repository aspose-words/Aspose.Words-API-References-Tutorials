---
title: Ignore Text Inside Delete Revisions
linktitle: Ignore Text Inside Delete Revisions
second_title: Aspose.Words for .NET API Reference
description: Learn how to use the "Ignore Text Inside Delete Revisions" feature of Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

In this article, we will explore the C# source code above to understand how to use the "Ignore Text Inside Delete Revisions" feature in the Aspose.Words for .NET library. This feature is useful when we want to ignore text inside deletion revisions when working with documents.

## Overview of the Aspose.Words for .NET library

Before diving into the code details, let me briefly introduce the Aspose.Words for .NET library. It is a powerful library that allows creating, modifying and converting Word documents in .NET applications. It offers many advanced features for working with documents, including revision management.

## Understanding the "Ignore Text Inside Delete Revisions" feature

The "Ignore Text Inside Delete Revisions" feature in Aspose.Words for .NET allows you to specify whether text inside delete revisions should be ignored during certain operations, such as finding and replacing text. When this feature is enabled, deleted text inside revisions is not considered during operations.

## Step 1: Creating a new document using Aspose.Words for .NET

Before we start manipulating text in a document, we need to create a new document using Aspose.Words for .NET. It can be done by instantiating a `Document` object:

```csharp
Document doc = new Document();
```

## Step 2: Inserting non-revised text into the document

Once we have a document, we can insert unreviewed text using a `DocumentBuilder` object. For example, to insert the text "Deleted Text", we can use the `Writeln` and `Write` methods:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Step 3: Removing a paragraph with tracking revisions

To illustrate the use of the "Ignore Text Inside Delete Revisions" feature, we will delete a paragraph from the document using revision tracking. This will allow us to see how this feature affects subsequent operations.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Step 4: Applying the "Ignore Text Inside Delete Revisions" feature

Now that we have prepared our document by deleting a paragraph, we can enable the "Ignore Text Inside Delete Revisions" feature using a `FindReplaceOptions` object. We will set the `IgnoreDeleted` property to `true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Step 5: Using regular expressions for find and replace

To perform search and replace operations on the text of the document, we will use regular expressions. In our example, we will search for all occurrences of the letter "e" and replace them with an asterisk "*". .NET `Regex` class is utilized for this:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Step 6: Displaying the modified document output

After applying the search and replace, we can display the changed content of the document using the `GetText` method:

```csharp
Console.WriteLine(doc.GetText());
```

## Step 7: Modifying the options to include deleted text

If we want to include deleted text in the output result, we can change the options to not ignore deleted text. For this we will set the `IgnoreDeleted` property to `false`:

```csharp
options. IgnoreDeleted = false;
```

## Step 8: Outputting the modified document with deleted text

After changing the options, we can perform the search and replace again to get the result with the deleted text included:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Example source code for Ignore Text Inside Delete Revisions using Aspose.Words for .NET

Here is the full sample source code to demonstrate the use of the "Ignore Text Inside Delete Revisions" feature with Aspose.Words for .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insert non-revised text.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Remove first paragraph with tracking revisions.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Conclusion

In this article, we explored the C# source code to understand how to use the "Ignore Text Inside Delete Revisions" feature in Aspose.Words for .NET. This feature is useful for ignoring text inside deletion revisions when manipulating documents. We followed a step-by-step guide to create a document, insert text, delete a paragraph with revision tracking, apply the "Ignore Text Inside Delete Revisions" feature, and perform find and replace operations.


