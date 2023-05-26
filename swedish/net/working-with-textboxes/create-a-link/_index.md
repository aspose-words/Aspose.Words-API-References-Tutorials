---
title: Skapa en länk
linktitle: Skapa en länk
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar en länk mellan TextBoxes i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-textboxes/create-a-link/
---

## Steg 1: Konfigurera dokumentet och skapa TextBox-former

 För att börja måste vi ställa in dokumentet och skapa två TextBox-former. Följande kod initierar en ny instans av`Document` klass och skapar två textruteformer:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Steg 2: Skapa en länk mellan TextBoxes

 Vi kommer nu att skapa en länk mellan de två textrutorna med hjälp av`IsValidLinkTarget()` metoden och`Next` egenskapen för den första textrutan.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 De`IsValidLinkTarget()` metod kontrollerar om den andra textrutan kan vara ett giltigt mål för länken till den första textrutan. Om valideringen lyckas,`Next` egenskapen för den första textrutan är inställd på den andra textrutan, vilket skapar en länk mellan de två.

### Exempel på källkod att länka till Aspose.Words för .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```