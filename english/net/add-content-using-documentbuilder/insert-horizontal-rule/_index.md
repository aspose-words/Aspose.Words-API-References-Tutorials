---
title: Insert Horizontal Rule
linktitle: Insert Horizontal Rule
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert horizontal rules in Word documents using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-horizontal-rule/
---

In this comprehensive example, you will learn how to insert a horizontal rule into a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to add horizontal rules to your documents for visual separation and organization.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert a Horizontal Rule
Next, use the Writeln method of the DocumentBuilder class to add a descriptive text and then insert a horizontal rule:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Step 3: Save the Document
After inserting the horizontal rule, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Example Source Code for Insert Horizontal Rule using Aspose.Words for .NET
Here is the complete source code for inserting a horizontal rule using Aspose.Words for .NET:
Horizontal rules are useful for various scenarios, such as dividing sections, creating visual breaks, or highlighting important information.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Insert a horizontal rule shape into the document.");
	builder.InsertHorizontalRule();

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
	
```

Remember to adjust the code according to your specific requirements and enhance it with additional functionality as needed.

## Conclusion
Congratulations! You have successfully learned how to insert a horizontal rule into a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now visually separate and organize your documents using horizontal rules.


