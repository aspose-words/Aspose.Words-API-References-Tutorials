---
title: Insert Floating Image
linktitle: Insert Floating Image
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert floating images in Word documents using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-floating-image/
---

In this comprehensive example, you will learn how to insert a floating image into a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to add images with customizable positioning and wrapping options to your documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert a Floating Image
Next, use the InsertImage method of the DocumentBuilder class to insert a floating image. Provide the image file path, relative horizontal and vertical position, width, height, and wrapping options as parameters:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Step 3: Save the Document
After inserting the floating image, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Example Source Code for Insert Floating Image using Aspose.Words for .NET
Here is the complete source code for inserting a floating image using Aspose.Words for .NET:
Floating images are useful for various scenarios, such as adding logos, illustrations, or decorative elements that can be positioned independently from the document's text.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertImage(ImagesDir + "Transparent background logo.png",
		RelativeHorizontalPosition.Margin,
		100,
		RelativeVerticalPosition.Margin,
		100,
		200,
		100,
		WrapType.Square);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
	
```

Remember to adjust the code according to your specific requirements, including the image file path and desired positioning and wrapping options.

## Conclusion
Congratulations! You have successfully learned how to insert a floating image into a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now enhance your documents with visually appealing and customizable floating images.


