---
title: Insert Inline Image In Word Document
linktitle: Insert Inline Image In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to insert inline images in Word documents using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-inline-image/
---
In this comprehensive tutorial, you will learn how to insert inline images into a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to add images directly into the text of your documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert an Inline Image
Next, use the InsertImage method of the DocumentBuilder class to insert an inline image into the document. Provide the image file path as a parameter:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Step 3: Save the Document
After inserting the inline image, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Example Source Code for Insert Inline Image using Aspose.Words for .NET
Here is the complete source code for inserting an inline image using Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Conclusion
Congratulations! You have successfully learned how to insert inline images into a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now add images seamlessly within the text of your documents.

Inline images are useful for various scenarios, such as adding illustrations, logos, or other visual elements directly into the flow of the document.

### FAQ's for insert inline image in word document

#### Q: Can I resize the inline images within the Word document?

A: Yes, you can resize the inline images using Aspose.Words for .NET. After inserting the image, you can manipulate its size by adjusting the width and height properties of the Shape object representing the image.

#### Q: Is it possible to add alt text to inline images for accessibility purposes?

A: Yes, you can add alt text to inline images to enhance accessibility. Aspose.Words for .NET supports the addition of alt text to images, allowing screen readers and other assistive technologies to describe the image content to visually impaired users.

#### Q: Can I apply formatting or styles to the inline images?

A: Absolutely! Aspose.Words for .NET provides extensive formatting options for inline images. You can apply various styles, borders, effects, and other formatting attributes to the images to match your document's visual design.

#### Q: Does Aspose.Words for .NET support inserting images from a stream or byte array?

A: Yes, you can insert inline images from streams or byte arrays using Aspose.Words for .NET. This allows you to work with images loaded from external sources or dynamically generated images.

#### Q: Can I insert images at specific positions within the text content?

A: Yes, the DocumentBuilder class in Aspose.Words for .NET provides precise control over the insertion position of inline images. You can specify the exact location within the text where the image should be inserted.
