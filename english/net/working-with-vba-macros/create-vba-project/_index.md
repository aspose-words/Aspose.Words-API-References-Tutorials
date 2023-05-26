---
title: Create Vba Project
linktitle: Create Vba Project
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to create a VBA project in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-vba-macros/create-vba-project/
---

In this tutorial, we are going to tell you how to create a VBA project in a Word document using the Aspose.Words library for .NET. Creating a VBA project allows you to add custom VBA code to your Word document. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Create a new VBA document and project
Next, we will create a new document by instantiating the `Document` class and an empty VBA project by instantiating the `VbaProject` class.

```csharp
// Create a new document
Document doc = new Document();

// Create a new VBA project
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Step 3: Create a new module and specify macro source code
We will create a new module by instantiating the `VbaModule` class and specifying the macro name, type (procedural module) and source code.

```csharp
// Create a new module
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Add the module to the VBA project
doc.VbaProject.Modules.Add(module);
```

## Step 4: Save the document
Finally, we will save the document with the VBA project created in a file.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Sample source code for Create Vba Project using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Create a new module and specify a macro source code.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Add module to the VBA project.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Conclusion
In this tutorial, we saw how to create a VBA project in a Word document using Aspose.Words for .NET. Creating a VBA project allows you to add and customize VBA code in your Word document. Feel free to use this feature to automate tasks or add custom functionality to your Word documents.

