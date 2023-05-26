---
title: Check DrawingML Text Effect
linktitle: Check DrawingML Text Effect
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to check DrawingML text effects in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/check-drawingml-text-effect/
---

In this tutorial, we will walk you through how to check DrawingML text effects in a Word document using Aspose.Words Library for .NET. Checking DrawingML text effects allows you to determine if a specific effect is applied to part of the text. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project
- A Word document containing DrawingML text effects

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document and check the text effects
Next, we'll load the Word document and access the collection of runs (character sequences) in the first paragraph of the body of the document. Next, we'll check if any specific DrawingML text effects are applied to the font of the first run.

```csharp
// Load the document
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Check DrawingML text effects
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Sample source code for Check DMLText Effect using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// One run might have several Dml text effects applied.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Conclusion
In this tutorial, we saw how to check DrawingML text effects in a Word document using Aspose.Words for .NET. Checking DrawingML text effects allows you to identify parts of text that have specific effects applied. Feel free to use this feature to manipulate and analyze text effects in your Word documents.

