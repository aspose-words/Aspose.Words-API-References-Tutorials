---
title: Skapa länk i Word
linktitle: Skapa länk i Word
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar länk i word mellan TextBoxes i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-textboxes/create-a-link/
---
Den här steg-för-steg-guiden förklarar hur man skapar länk i word mellan två textrutor i ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Du kommer att lära dig hur du konfigurerar dokumentet, skapar textruteformerna, kommer åt textrutorna, kontrollerar länkmålets giltighet och slutligen skapar själva länken.

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
## Slutsats

Grattis! Du har nu lärt dig hur du skapar en länk mellan två textrutor i ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Med hjälp av den här steg-för-steg-guiden kunde du ställa in dokumentet, skapa textruteformerna, komma åt textrutorna, kontrollera giltigheten av länkmålet och slutligen skapa själva länken.

### Vanliga frågor för att skapa länkar i Word

#### F: Vilket bibliotek används för att länka textrutor i Word med Aspose.Words för .NET?

S: För att länka textrutor i Word med Aspose.Words för .NET, är biblioteket som används Aspose.Words for .NET.

#### F: Hur kontrollerar man om länkmålet är giltigt innan man skapar länken?

 S: Innan du skapar länken mellan textrutor kan du använda`IsValidLinkTarget()` metod för att kontrollera om länkmålet är giltigt. Denna metod validerar om den andra textrutan kan vara ett giltigt mål för länken från den första textrutan.

#### F: Hur skapar man en länk mellan två textrutor?

 S: För att skapa en länk mellan två textrutor måste du ställa in`Next`egenskapen för den första textrutan till den andra textrutan. Se till att du har kontrollerat giltigheten av länkmålet i förväg med hjälp av`IsValidLinkTarget()` metod.

#### F: Är det möjligt att skapa länkar mellan andra element än textrutor?

S: Ja, med Aspose.Words-biblioteket för .NET är det möjligt att skapa länkar mellan olika element som stycken, tabeller, bilder etc. Processen kommer att variera beroende på det specifika objektet du vill länka.

#### F: Vilka andra funktioner kan läggas till i textrutor i Word med Aspose.Words för .NET?

S: Med Aspose.Words för .NET kan du lägga till många andra funktioner i textrutor, såsom textformatering, lägga till bilder, ändra stilar etc. Du kan utforska Aspose.Words för .NET-dokumentationen för att ta reda på alla funktionerna tillgängliga.