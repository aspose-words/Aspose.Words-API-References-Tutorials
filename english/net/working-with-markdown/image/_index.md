---
title: Image
linktitle: Image
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert and customize image with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/image/
---

In this example, we will explain how to use the image feature with Aspose.Words for .NET. Pictures allow you to insert illustrations and graphics into a document.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Inserting an image

We can insert an image using the `Shape` class and specifying the type of image, here `ShapeType.Image`. We also set the wrap type of the image to `WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Step 3: Image Customization

We customize the image by specifying its full path, for example `"/attachment/1456/pic001.png"`, and adding a title to the image.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Example source code for images with Aspose.Words for .NET

```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Insert image.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Congratulation ! You have now learned how to use the images feature with Aspose.Words for .NET.


### FAQ's

#### Q: How can I insert an image from a local file into Aspose.Words?

A: To insert an image from a local file into Aspose.Words, you can use the `Shape` class and the `InsertImage` method.

#### Q: Can I insert an image from a URL in Aspose.Words?

A: Yes, you can insert an image from a URL in Aspose.Words. You can use the same `InsertImage` method and specify the image URL instead of the local file path.

#### Q: How can I resize an image in Aspose.Words?

A: To resize an image in Aspose.Words, you can use the `Width` and `Height` properties of the `Shape` object.

#### Q: Can I apply filters to images in Aspose.Words?

A: Yes, you can apply filters to images in Aspose.Words. For example, you can apply a blur filter to an image using the `ApplyGaussianBlur` method of the `Shape` object.

#### Q: How can I replace one image with another in Aspose.Words?

A: To replace one image with another in Aspose.Words, you can use the `Replace` method of the `Shape` class. This method takes as parameter the `Shape` object of the image to be replaced and the `Shape` object of the new image.
