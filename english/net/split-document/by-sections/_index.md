---
title: By Sections
linktitle: By Sections
second_title: Aspose.Words for .NET API Reference
description: Learn how to split a Word document into separate sections using Aspose.Words for .NET with complete code example.
type: docs
weight: 10
url: /net/split-document/by-sections/
---

In this example, we will show you how to divide a Word document into separate sections using the By Sections feature of Aspose.Words for .NET. Follow the steps below to understand the source code and get separate documents for each section.

## Step 1: Loading the document

To start, we need to specify the directory of your document and load the document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Step 2: Divide the document into sections

Now we are going to iterate through each section of the document and break the document into smaller parts, section by section. Here's how to do it:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Split the document into smaller parts, in this case, separating it by section.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Save each section as a separate document.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Example source code for By Sections using Aspose.Words for .NET

Here is the complete source code for the By Sections feature of Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	for (int i = 0; i < doc.Sections.Count; i++)
	{
		// Split a document into smaller parts, in this instance, split by section.
		Section section = doc.Sections[i].Clone();

		Document newDoc = new Document();
		newDoc.Sections.Clear();

		Section newSection = (Section) newDoc.ImportNode(section, true);
		newDoc.Sections.Add(newSection);

		// Save each section as a separate document.
		newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
	}

```

With this code you will be able to split a Word document into separate sections using Aspose.Words for .NET.

Now you can easily work with specific sections.


