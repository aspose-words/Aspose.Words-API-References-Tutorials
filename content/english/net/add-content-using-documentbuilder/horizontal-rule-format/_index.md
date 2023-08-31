---
title: Horizontal Rule Format In Word Document
linktitle: Horizontal Rule Format In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to format horizontal rules in Word documents using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/horizontal-rule-format/
---
In this comprehensive example, you will learn how to format a horizontal rule in a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to customize the alignment, width, height, color, and other properties of a horizontal rule.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a DocumentBuilder and Insert a Horizontal Rule
To start, create a DocumentBuilder object and use the InsertHorizontalRule method to insert a horizontal rule:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Step 2: Access the Horizontal Rule Format
Next, access the HorizontalRuleFormat property of the Shape object to retrieve the formatting options:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Step 3: Customize the Formatting Options
Now, you can customize various formatting options for the horizontal rule. For example, you can adjust the alignment, width, height, color, and shading:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Step 4: Save the Document
After formatting the horizontal rule, save the document to a file using the Save method of the Document object:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Example Source Code for Horizontal Rule Format using Aspose.Words for .NET
Here is the complete source code for formatting a horizontal rule using Aspose.Words for .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Remember to adjust the code according to your specific requirements and enhance it with additional functionality as needed.

## Conclusion
Congratulations! You have successfully learned how to format a horizontal rule in a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now customize the appearance of horizontal rules to enhance your document's visual layout.

Experiment with different formatting options to achieve the desired style and effect for your horizontal rules.

### FAQ's for horizontal rule format in word document

#### Q: Can I apply different colors to the horizontal rule?

A: Absolutely! With Aspose.Words for .NET, you can easily customize the color of the horizontal rule by setting the Color property to the desired color value. This allows you to match the horizontal rule with your document's overall design.

#### Q: Is it possible to adjust the width and height of the horizontal rule?

A: Yes, you have full control over the width and height of the horizontal rule. By modifying the WidthPercent and Height properties, you can achieve the desired dimensions for the horizontal rule.

#### Q: Can I change the alignment of the horizontal rule within the document?

A: Certainly! Aspose.Words for .NET enables you to specify the alignment of the horizontal rule using the Alignment property. You can choose from various options like Center, Left, Right, and Justified.

#### Q: Can I apply shading or background color to the horizontal rule?

A: Yes, you can add shading or background color to the horizontal rule. By default, the NoShade property is set to true, but you can set it to false and define the shading using the appropriate methods.

#### Q: Can I insert multiple horizontal rules in a single document?

A: Absolutely! You can insert multiple horizontal rules in a Word document using Aspose.Words for .NET. Simply repeat the steps in the tutorial as needed to add as many horizontal rules as you require.
