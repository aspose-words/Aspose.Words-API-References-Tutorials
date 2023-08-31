---
title: Insert Horizontal Rule In Word Document
linktitle: Insert Horizontal Rule In Word Document
second_title: Aspose.Words Document Processing API
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

### FAQ's for insert horizontal rule in word document

#### Q: Can I customize the appearance of the horizontal rule?

A: Yes, absolutely! Aspose.Words for .NET provides various properties to customize the appearance of the horizontal rule. You can adjust its width, height, alignment, color, and shading to match your document's aesthetics.

#### Q: Can I add multiple horizontal rules in a single document?

A: Certainly! You can insert as many horizontal rules as needed in a Word document using Aspose.Words for .NET. Simply repeat the insertion process to add multiple visual breaks or section dividers.

#### Q: Are horizontal rules compatible with other file formats, like PDF?

A: Yes, horizontal rules inserted using Aspose.Words for .NET are compatible with various file formats, including DOCX and PDF. This means you can export your documents in different formats while retaining the horizontal rules.

#### Q: Can I programmatically insert a horizontal rule at specific positions in the document?

A: Absolutely! Aspose.Words for .NET allows you to position the horizontal rule at specific locations within the document programmatically. You can control its placement based on your document's content and structure.

#### Q: Is Aspose.Words for .NET suitable for both desktop and web applications?

A: Yes, Aspose.Words for .NET is versatile and can be used in both desktop and web applications. Whether you're building a Windows application or a web-based system, you can integrate the library effortlessly.
