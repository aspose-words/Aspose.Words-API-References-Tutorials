---
title: Cleanup Unused Styles And Lists
linktitle: Cleanup Unused Styles And Lists
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to cleaning up unused styles and lists in a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

In this tutorial, we will walk you through the C# source code to clean up unused styles and lists with Aspose.Words for .NET. This feature allows you to remove styles and lists that are not used in a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document containing the unused styles and lists that we want to clean up. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Count styles and lists before cleaning

Before cleaning, we will count the number of styles and lists present in the document. Use the following code to display the counters:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

These instructions show the number of styles and lists present in the document before cleaning.

## Step 4: Clean up unused styles and lists

Now let's clean up unused styles and lists from the document. Use the following code to perform the cleanup:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

This code cleans up unused styles and lists from the document using the specified options. In this example, we enabled the `UnusedStyles` option to remove unused styles and disabled the `UnusedLists` option to keep the lists even if they are not used.

## Step 5: Count styles and lists after cleaning

After doing the cleanup, we'll count the styles and lists again to check if they've been collapsed. Use the following code to display the new counters:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

These instructions show the numbers of styles and lists remaining after cleaning.

### Example source code for Cleanup Unused Styles And Lists using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Combined with the built-in styles, the document now has eight styles.
	// A custom style is marked as "used" while there is any text within the document
	// formatted in that style. This means that the 4 styles we added are currently unused.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	// Cleans unused styles and lists from the document depending on given CleanupOptions. 
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to clean up unused styles and lists from a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily apply this feature to your own documents.


