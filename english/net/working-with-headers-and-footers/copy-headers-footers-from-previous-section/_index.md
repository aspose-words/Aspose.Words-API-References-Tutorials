---
title: Copy Headers Footers From Previous Section
linktitle: Copy Headers Footers From Previous Section
second_title: Aspose.Words for .NET API Reference
description: Learn how to copy headers and footers from the previous section in Word documents using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

In this step-by-step tutorial, we will guide you on how to copy headers and footers from the previous section in a Word document using Aspose.Words for .NET. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Accessing the Previous Section

First, retrieve the previous section by accessing the `PreviousSibling` property of the current section:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Step 2: Checking for Previous Section

Next, check if a previous section exists. If there is no previous section, we simply return:

```csharp
if (previousSection == null)
    return;
```

## Step 3: Clearing and Copying Headers and Footers

To copy the headers and footers from the previous section to the current section, we clear the existing headers and footers in the current section and then iterate through the headers and footers of the previous section to add cloned copies to the current section:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Step 4: Saving the Document

Finally, save the modified document:

```csharp
doc.Save("OutputDocument.docx");
```

That's it! You have successfully copied headers and footers from the previous section to the current section in a Word document using Aspose.Words for .NET.

### Example source code for Copy Headers Footers From Previous Section using Aspose.Words for .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Feel free to use this code in your own projects and modify it according to your specific requirements.
