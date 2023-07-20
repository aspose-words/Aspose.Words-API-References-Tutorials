---
title: Apply Borders And Shading To Paragraph In Word Document
linktitle: Apply Borders And Shading To Paragraph In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to apply borders and shading to a paragraph in word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/apply-borders-and-shading-to-paragraph/
---
In this tutorial, we are going to show you how to apply borders and shading to a paragraph in word document using the functionality of Aspose.Words for .NET. Follow the steps below to understand the source code and apply formatting changes.

## Step 1: Creating and configuring the document

To begin, create a new document and an associated DocumentBuilder object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Border configuration

Now let's configure the paragraph borders by specifying the border style for each side. Here's how:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Step 3: Infill Setup

We will now configure the paragraph fill by specifying the texture and the fill colors. Here's how:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Step 4: Add content

We are going to add some formatted content to the paragraph. Here's how:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Step 3: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Example source code for Apply Borders And Shading To Paragraph using Aspose.Words for .NET

Here is the complete source code for the Apply Borders and shading to Paragraph feature with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Conclusion

In this tutorial, we learned how to apply borders and shading to a paragraph in a Word document using Aspose.Words for .NET. By configuring the paragraph's `Borders` and `Shading` properties, we were able to set the border style, line color, and fill color for the paragraph. Aspose.Words for .NET provides powerful formatting capabilities to customize the appearance of paragraphs and enhance the visual representation of your documents.

### FAQ's

#### Q: How do I apply borders and shading to a paragraph in a Word document using Aspose.Words for .NET?

A: To apply borders and shading to a paragraph in a Word document using Aspose.Words for .NET, follow these steps:
1. Create a new document and a `DocumentBuilder` object.
2. Configure the paragraph borders by accessing the `Borders` property of the `ParagraphFormat` and setting the border style for each side.
3. Configure the paragraph fill by accessing the `Shading` property of the `ParagraphFormat` and specifying the texture and fill colors.
4. Add content to the paragraph using the `Write` method of the `DocumentBuilder`.
5. Save the document using the `Save` method.

#### Q: How do I set the border style for each side of the paragraph?

A: To set the border style for each side of the paragraph, you can access the `Borders` property of the `ParagraphFormat` and set the `LineStyle` property for each `BorderType` (e.g., `BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom`). You can specify different line styles such as `LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, etc.

#### Q: How do I specify the texture and fill colors for the paragraph shading?

A: To specify the texture and fill colors for the paragraph shading, you can access the `Shading` property of the `ParagraphFormat` and set the `Texture` property to a desired texture index (e.g., `TextureIndex.TextureDiagonalCross`). You can also set the `BackgroundPatternColor` and `ForegroundPatternColor` properties to the desired colors using the `System.Drawing.Color` class.
