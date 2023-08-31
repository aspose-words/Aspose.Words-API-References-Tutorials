---
title: Cleanup Duplicate Style
linktitle: Cleanup Duplicate Style
second_title: Aspose.Words Document Processing API
description: Step by step guide to clean up duplicate styles in a document using Aspose.Words for .NET. Full source code included.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

In this tutorial, we will walk you through step by step C# source code to clean up duplicate styles with Aspose.Words for .NET. This feature helps to remove duplicate styles from a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document that we want to clean up. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Count styles before cleaning

Before proceeding with the cleaning, we will count the number of styles present in the document. Use the following code to display the style count:

```csharp
Console.WriteLine(doc.Styles.Count);
```

This statement displays the number of styles present in the document.

## Step 4: Clean up duplicate styles

Now let's clean up duplicate styles from the document. Use the following code to perform the cleanup:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

This code cleans up duplicate styles from the document using the specified options. In this example, we enabled the `DuplicateStyle` option to clean up duplicate styles.

## Step 5: Count styles after cleaning

After doing the cleaning, we will count the number of styles again to check if it has decreased. Use the following code to display the new styles count:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

This statement displays the number of styles remaining after cleaning.

### Example source code for Cleanup Duplicate Style using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Count of styles before Cleanup.
	Console.WriteLine(doc.Styles.Count);

	// Cleans duplicate styles from the document.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Count of styles after Cleanup was decreased.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```