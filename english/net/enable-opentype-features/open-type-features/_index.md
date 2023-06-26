---
title: Open Type Features
linktitle: Open Type Features
second_title: Aspose.Words for .NET API Reference
description: Learn how to enable and use Open Type features in Aspose.Words for .NET
type: docs
weight: 10
url: /net/enable-opentype-features/open-type-features/
---

In this comprehensive tutorial, you will learn how to enable and utilize Open Type features in Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to work with Open Type features in your Word documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Load the Document
To start, load the document using the Document class:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Step 2: Enable Open Type Features
To enable Open Type features, set the TextShaperFactory property of the LayoutOptions class to an instance of the desired text shaper factory. In this example, we use the HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Step 3: Save the Document
After enabling the Open Type features, save the document in the desired output format, such as PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Example Source Code for Open Type Features using Aspose.Words for .NET
Here is the complete source code for using Open Type features in Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusion
Congratulations! You have successfully learned how to enable and utilize Open Type features in Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now work with Open Type features in your Word documents.

Open Type features offer enhanced typography and text shaping capabilities, allowing you to create visually appealing and professional-looking documents. Experiment with different text shaper factories and explore the possibilities of Open Type features in your projects.

### FAQ's

#### Q: How do I enable OpenType features in Aspose.Words for .NET?

A: To enable OpenType features in Aspose.Words for .NET, you need to follow the steps mentioned in the tutorial.

#### Q: What OpenType features are supported in Aspose.Words for .NET?

A: Aspose.Words for .NET supports several OpenType features, such as ligatures, glyph variations, contextual substitutions, and more.

#### Q: How can I check if an OpenType feature is supported in a specific font?

A: You can check if an OpenType feature is supported in a specific font using the `Font.OpenTypeFeatures` method in Aspose.Words for .NET.

#### Q: What other text formatting features does Aspose.Words for .NET support?

A: Apart from OpenType features, Aspose.Words for .NET also supports other text formatting features like formatting paragraphs, creating tables, adding images, etc.

#### Q: Can I use OpenType features in all versions of Aspose.Words for .NET?

A: OpenType features are supported in newer versions of Aspose.Words for .NET. Make sure you are using a compatible version to benefit from these features.
