---
title: Obegränsade redigerbara regioner i Word-dokument
linktitle: Obegränsade redigerbara regioner i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar obegränsade redigerbara områden i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/unrestricted-editable-regions/
---
I den här handledningen guidar vi dig genom stegen för att använda funktionen för obegränsade redigerbara områden i Aspose.Words för .NET. Den här funktionen låter dig definiera områden i ett Word-dokument där innehåll kan redigeras utan begränsningar, även om resten av dokumentet är skrivskyddat. Följ stegen nedan:

## Steg 1: Laddar dokumentet och ställer in skydd

Börja med att ladda det befintliga dokumentet:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Skydda dokumentet genom att ställa in skrivskyddstyp och lösenord

## Steg 2: Skapa ett redigerbart område

Börja med att skapa ett redigerbart område med hjälp av objekten EditableRangeStart och EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Ett EditableRange-objekt skapas för EditableRangeStart som vi just skapade.
EditableRange editableRange = edRangeStart.EditableRange;

// Lägg något inom det redigerbara intervallet.
builder.Writeln("Paragraph inside first editable range");

// Ett redigerbart område är välformat om det har en början och ett slut.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Steg 3: Lägg till innehåll utanför redigerbara områden

Du kan lägga till innehåll utanför de redigerbara områdena, som förblir skrivskyddade:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Steg 4: Spara dokumentet

Slutligen, spara det ändrade dokumentet:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara dokumentet med redigerbara områden.

### Exempel på källkod för obegränsade redigerbara regioner med Aspose.Words för .NET

Här är den fullständiga källkoden för obegränsade redigerbara områden med Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda upp ett dokument och gör det som skrivskyddat.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Starta ett redigerbart intervall.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Ett EditableRange-objekt skapas för EditableRangeStart som vi just skapade.
EditableRange editableRange = edRangeStart.EditableRange;

// Lägg något inom det redigerbara intervallet.
builder.Writeln("Paragraph inside first editable range");

// Ett redigerbart område är välformat om det har en början och ett slut.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Genom att följa dessa steg kan du enkelt skapa obegränsade redigerbara områden i ditt Word-dokument med Aspose.Words för .NET.

## Slutsats
I den här handledningen lärde vi oss hur man skapar obegränsade redigerbara regioner i ett Word-dokument med Aspose.Words för .NET. Genom att följa de angivna stegen kan du definiera specifika områden i dokumentet där användare fritt kan redigera innehållet samtidigt som resten av dokumentet är skrivskyddat. Aspose.Words för .NET erbjuder kraftfulla funktioner för dokumentskydd och anpassning, vilket ger dig kontroll över redigeringsmöjligheterna för dina Word-dokument.

### Vanliga frågor för obegränsade redigerbara regioner i word-dokument

#### F: Vilka är obegränsade redigerbara regioner i Aspose.Words för .NET?

S: Obegränsade redigerbara regioner i Aspose.Words för .NET är områden i ett Word-dokument där innehåll kan redigeras utan några begränsningar, även om resten av dokumentet är inställt som skrivskyddat. Dessa regioner ger ett sätt att definiera specifika delar av dokumentet som användare kan ändra samtidigt som det övergripande dokumentskyddet bibehålls.

#### F: Hur kan jag skapa obegränsade redigerbara regioner med Aspose.Words för .NET?

S: För att skapa obegränsade redigerbara regioner i ett Word-dokument med Aspose.Words för .NET kan du följa dessa steg:
1.  Ladda det befintliga dokumentet med hjälp av`Document` klass.
2.  Ställ in dokumentskyddet på skrivskyddat med hjälp av`Protect` metod för`Document` objekt.
3.  Använd`DocumentBuilder` klass för att skapa ett redigerbart intervall genom att lägga till en`EditableRangeStart` föremål och ett`EditableRangeEnd` objekt.
4.  Lägg till innehåll inom det redigerbara intervallet med hjälp av`DocumentBuilder`.
5.  Spara det ändrade dokumentet med hjälp av`Save` metod för`Document` objekt.

#### F: Kan jag ha flera obegränsade redigerbara regioner i ett Word-dokument?

S: Ja, du kan ha flera obegränsade redigerbara regioner i ett Word-dokument. För att uppnå detta kan du skapa flera uppsättningar av`EditableRangeStart` och`EditableRangeEnd` objekt med hjälp av`DocumentBuilder` klass. Varje uppsättning objekt kommer att definiera en separat redigerbar region där användare kan ändra innehållet utan några begränsningar.

#### F: Kan jag kapsla redigerbara regioner inom varandra?

 S: Nej, du kan inte kapsla redigerbara regioner inom varandra med Aspose.Words för .NET. Varje redigerbar region definierad av en`EditableRangeStart` och`EditableRangeEnd` paret ska vara oberoende och inte överlappa eller vara kapslat inom en annan redigerbar region. Kapslade redigerbara regioner stöds inte.

#### F: Kan jag ta bort skrivskyddet från dokumentet inom en redigerbar region?

S: Nej, du kan inte ta bort skrivskyddet från dokumentet inom en redigerbar region. Det skrivskyddade skyddet tillämpas på hela dokumentet och det kan inte tas bort selektivt inom specifika redigerbara regioner. Syftet med de redigerbara regionerna är att tillåta innehållsändringar samtidigt som det övergripande dokumentet skrivskyddas.