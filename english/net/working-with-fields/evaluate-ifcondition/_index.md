---
title: Evaluate IF Condition
linktitle: Evaluate IF Condition
second_title: Aspose.Words for .NET API Reference
description: Step by step guide for evaluating the IF condition in your Word documents with Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-fields/evaluate-ifcondition/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Evaluate IF Condition" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Creating the document generator

In the provided code, we start by creating a document generator.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Insert the IF field

We use the `InsertField()` method to insert the IF field into the document specifying the condition to evaluate.

```csharp
FieldIf field = (FieldIf) builder.InsertField("IF 1 = 1", null);
```

Here we used the condition "1=1" as an example, but you can customize the condition as needed.

## Step 3: Evaluate the IF condition

The `EvaluateCondition()` method is used to evaluate the condition of the IF field.

```csharp
FieldIfComparisonResult actualResult = field.EvaluateCondition();
```

The `actualResult` variable contains the result of the condition evaluation.

### Sample Source Code for Evaluate IF Condition with Aspose.Words for .NET

```csharp
// Creation of the document generator.
DocumentBuilder builder = new DocumentBuilder();

// Insert the IF field into the document.
FieldIf field = (FieldIf) builder.InsertField("IF 1 = 1", null);

// Evaluate the IF condition.
FieldIfComparisonResult actualResult = field.EvaluateCondition();

// Display the result of the evaluation.
Console.WriteLine(actualResult);
```

In this example, we've created a document builder, inserted an IF field with a condition specified, and then evaluated the condition. The result of the evaluation is then displayed in the console.

This concludes our guide on using the "Evaluate IF Condition" feature with Aspose.Words for .NET.

