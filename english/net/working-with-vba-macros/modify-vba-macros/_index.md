---
title: Modify Vba Macros Of A Word Document
linktitle: Modify Vba Macros Of A Word Document
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to edit VBA macros of a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-vba-macros/modify-vba-macros/
---
In this tutorial, we will explain how to modify VBA macros of a Word document using the Aspose.Words library for .NET. Editing VBA macros allows you to update existing VBA code in your Word document. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project
- A Word document containing VBA macros that you want to modify

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document containing the VBA macros
Next, we will load the Word document containing the VBA macros that we want to modify.

```csharp
// Load the document containing the VBA macros
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Step 3: Modify the macro source code
We are now going to modify the source code of the first macro of the VBA project. Replace the `newSourceCode` variable with the new source code you want to use.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Step 4: Save the modified document
Finally, we'll save the modified document with the updated VBA macros to a file.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Sample source code for Modify Vba Macros using Aspose.Words for .NET
 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Conclusion
In this tutorial, we saw how to edit VBA macros in a Word document using Aspose.Words for .NET. Editing VBA macros allows you to update existing VBA code in your document to make changes or improvements. Feel free to use this feature to further customize and automate your Word documents.
