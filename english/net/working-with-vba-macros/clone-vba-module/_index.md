---
title: Clone Vba Module from a Word Document
linktitle: Clone Vba Module from a Word Document
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to clone a VBA module from a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-vba-macros/clone-vba-module/
---

In this tutorial, we are going to tell you how to clone a VBA module from a Word document with macros using the Aspose.Words library for .NET. Cloning a VBA module allows you to reuse or copy VBA code from one source document to another document. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project
- A Word document containing a VBA project with the module you want to clone

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load source document
Next, we'll load the source Word document, which contains the VBA project and the module we want to clone.

```csharp
// Load the source document
Document doc = new Document(dataDir + "VBA project.docm");
```

## Step 3: Create a new document with the VBA project and clone the module
We will create a new document with an empty VBA project and clone the specified module from the source document.

```csharp
// Create a new document with an empty VBA project
Document destDoc = new Document { VbaProject = new VbaProject() };

// Clone the module
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Step 4: Save the destination document
Finally, we'll save the destination document with the cloned VBA module to a file.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Sample source code for Clone Vba Module using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Conclusion
In this tutorial, we saw how to clone a VBA module from a Word document with macros using Aspose.Words for .NET. Cloning VBA modules allows you to easily reuse VBA code from one source document in another document. Feel free to use this feature to organize and manage your macros in different documents.

