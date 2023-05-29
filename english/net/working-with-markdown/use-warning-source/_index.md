---
title: Use Warning Source
linktitle: Use Warning Source
second_title: Aspose.Words for .NET API Reference
description: Learn how to use warning source with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/use-warning-source/
---

In this example, we are going to show you how to use warning source with Aspose.Words for .NET. The warning source indicates the origin of the warning when using the callback function.

## Step 1: Loading the document

We will load an existing document that contains warnings using the `Load` method of the `Document` class.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Step 3: Using the Warning Source

We'll use the warning source by setting the document's `WarningCallback` property to a collection of `WarningInfo` objects.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Step 4: Saving the document

Finally, we can save the document in the desired format.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Example Source Code for Using Warning Source with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Congratulation ! You have now learned how to use the warning source with Aspose.Words for .NET.
