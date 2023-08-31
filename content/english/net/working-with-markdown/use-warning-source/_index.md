---
title: Use Warning Source
linktitle: Use Warning Source
second_title: Aspose.Words Document Processing API
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

### FAQ's

#### Q: Can we customize the appearance of the "Warning" tag?

A: The formatting of the "Warning" tag depends on the Markdown renderer used. In most cases, you can customize the look by using CSS to target the `blockquote` tag in your document.

#### Q: Is it possible to add icons to the "Warning" tag?

A: Yes, it is possible to add icons to the "Warning" tag using HTML code in your Markdown document. You can insert a `span` tag with the appropriate class to display an icon next to the warning text.

#### Q: Is the "Warning" tag compatible with all Markdown readers?

A: The compatibility of the "Warning" tag depends on the Markdown rendering used. Most Markdown readers will support the `blockquote` tag to display highlighted text, but the exact appearance may vary.
