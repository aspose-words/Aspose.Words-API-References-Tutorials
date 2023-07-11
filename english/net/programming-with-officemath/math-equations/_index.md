---
title: Math Equations
linktitle: Math Equations
second_title: Aspose.Words Document Processing API
description: Learn how to add math equations to your Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-officemath/math-equations/
---

Aspose.Words for .NET is a powerful library for creating, editing, and manipulating Word documents in a C# application. Among the features offered by Aspose.Words is the possibility of adding mathematical equations to your documents. In this guide, we'll walk you through how to use the C# source code of Aspose.Words for .NET to add math equations to a Word document.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a popular library that makes working with Word documents easy and efficient. It offers a wide range of features for creating, editing and manipulating Word documents, including support for mathematical equations.

## Loading the Word document

The first step is to load the Word document to which you want to add a math equation. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Office math.docx");
```

In this example, we are loading the "Office math.docx" document located in the documents directory.

## Adding a math equation

Once the document is loaded, you can access the OfficeMath element in the document. Use the GetChild method of the Document class to get the OfficeMath item from the specified index. Here is an example :

```csharp
OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
```

In this example, we get the first OfficeMath item in the document.

## Configuring Math Equation Properties

You can configure various properties of the math equation using OfficeMath object properties. For example, you can set the display type of the math equation using the DisplayType property. Here is an example :

```csharp
officeMath.DisplayType = OfficeMathDisplayType.Display;
```

In this example, we set the display type of the math equation to "Display", which means the equation will be displayed on its own line.

Similarly, you can set the alignment of the math equation using the Justification property. Here is an example :

```csharp
officeMath.Justification = OfficeMathJustification.Left;
```

In this example, we set the alignment of the math equation to the left.

## Saving the document with the mathematical equation

Once you have configured the properties of the mathematical equation, you can save the modified document using the Save method of the Document class. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithOfficeMath.MathEquations.docx

");
```

In this example, we save the modified document as "WorkingWithOfficeMath.MathEquations.docx".

### Example source code for math equations with Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the Word document
Document doc = new Document(dataDir + "Office math.docx");

// Obtain the OfficeMath element
OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// Configure the properties of the mathematical equation
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

// Save the document with the mathematical equation
doc.Save(dataDir + "WorkingWithOfficeMath.MathEquations.docx");
```

## Conclusion

In this guide, we've covered how to use Aspose.Words for .NET to add math equations to a Word document using the provided C# source code. By following the steps provided, you can easily add math equations to your Word documents in your C# application. Aspose.Words offers tremendous flexibility and power for working with mathematical equations, allowing you to create professional, well-formatted documents.

