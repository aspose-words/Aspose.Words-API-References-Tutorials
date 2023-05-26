---
title: Convert Between Measurement Units
linktitle: Convert Between Measurement Units
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to converting between measurement units in a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/convert-between-measurement-units/
---

In this tutorial, we will walk you through the C# source code to convert between measurement units with Aspose.Words for .NET. This feature allows you to specify margins, header and footer distances, etc. in different units of measurement.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Creating the Document and Constructor

In this step we will create a new document and initialize the constructor. Use the following code:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Configure units of measure

Now we will convert the values for margins, header and footer distances, etc. in different units of measurement. Use the following code to specify values in specific measurement units:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

This code uses the `ConvertUtil` class of Aspose.Words to convert the specified values to inches (`InchToPoint`). You can also use other conversion methods available in the `ConvertUtil` class to convert values to other measurement units.

### Example source code for Convert Between Measurement Units using Aspose.Words for .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

You have now learned how to convert between measurement units when specifying margins, header and footer distances, etc. in a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily specify the values in the desired measurement units in your own documents.
