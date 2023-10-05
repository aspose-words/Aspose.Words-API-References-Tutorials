---
title: Obegränsad sektion i Word-dokument
linktitle: Obegränsad sektion i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du definierar obegränsade avsnitt i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/unrestricted-section/
---
I den här handledningen kommer vi att guida dig genom stegen för att använda den obegränsade sektionsfunktionen i Aspose.Words för .NET. Med den här funktionen kan du definiera specifika avsnitt i ett Word-dokument som inte är skyddade, även om resten av dokumentet är skyddat. Följ stegen nedan:

## Steg 1: Skapa dokumentet och sektionerna

Börja med att skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Lägg till innehåll i dokumentet
Använd DocumentBuilder-objektet för att lägga till innehåll i dokumentet och infoga avsnittsbrytningar:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Steg 3: Skydda dokument och sektioner

Sektionsskydd fungerar endast när dokumentskydd är aktiverat och endast redigering i formulärfält är tillåten. Du kan skydda dokumentet med metoden Protect() för Document-objektet:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Var noga med att ange rätt typ av skydd och ställ in önskat lösenord.

## Steg 4: Inaktivera skydd för en specifik sektion

Som standard är alla sektioner skyddade, men du kan selektivt inaktivera skyddet för en specifik sektion med hjälp av egenskapen ProtectedForForms för Section-objektet:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

I det här exemplet är skyddet inaktiverat för det första avsnittet.

## Steg 5: Spara dokumentet

Spara slutligen det ändrade dokumentet:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara dokumentet med obegränsade sektioner.

### Exempel på källkod för Unrestricted Section med Aspose.Words för .NET

Här är den fullständiga källkoden för den obegränsade delen med Aspose.Words för .NET:


```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Infoga två avsnitt med lite text.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Sektionsskydd fungerar bara när dokumentskyddet är vänt och endast redigering i formulärfält är tillåten.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Som standard är alla avsnitt skyddade, men vi kan selektivt stänga av skyddet.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Genom att följa dessa steg kommer du enkelt att kunna definiera obegränsade avsnitt i ditt Word-dokument med Aspose.Words för .NET.

## Slutsats

I den här handledningen utforskade vi den obegränsade sektionsfunktionen i Aspose.Words för .NET, som tillåter specifika avsnitt i ett Word-dokument att förbli oskyddade medan resten av dokumentet är skyddat. Genom att följa de angivna stegen kan du enkelt definiera avsnitt i ditt dokument där användare fritt kan redigera innehållet samtidigt som skyddet för andra avsnitt bibehålls. Aspose.Words för .NET erbjuder kraftfulla funktioner för dokumentskydd och anpassning, vilket ger dig kontroll över redigeringsbehörigheterna i dina Word-dokument.

### Vanliga frågor för obegränsad sektion i word-dokument

#### F: Vad är obegränsade sektioner i Aspose.Words för .NET?

S: Obegränsade avsnitt i Aspose.Words för .NET är specifika avsnitt i ett Word-dokument som inte är skyddade, även om resten av dokumentet är skyddat. Dessa avsnitt tillåter användare att ändra innehållet i dem samtidigt som skyddet för de återstående delarna av dokumentet bibehålls.

#### F: Hur kan jag skapa obegränsade sektioner med Aspose.Words för .NET?

S: För att skapa obegränsade avsnitt i ett Word-dokument med Aspose.Words för .NET, kan du följa dessa steg:
1.  Skapa en instans av`Document` klass och a`DocumentBuilder` objekt.
2.  Använd`DocumentBuilder` för att lägga till innehåll i dokumentet och infoga avsnittsbrytningar.
3.  Skydda dokumentet med hjälp av`Protect` metod för`Document` objekt, ange önskad skyddstyp och lösenord.
4.  Inaktivera skydd för en specifik sektion genom att ställa in`ProtectedForForms` motsvarande egendom`Section` invända mot`false`.
5. Spara det ändrade dokumentet.

#### F: Kan jag ha flera obegränsade sektioner i ett Word-dokument?

 S: Ja, du kan ha flera obegränsade sektioner i ett Word-dokument. Genom att selektivt inaktivera skydd för specifika sektioner med hjälp av`ProtectedForForms` egendom av`Section`objekt kan du definiera flera sektioner där användare fritt kan ändra innehållet samtidigt som andra sektioner skyddas.

#### Q4. Kan jag ta bort skyddet från en sektion som ursprungligen var skyddad?
 Ja, du kan ta bort skyddet från en sektion som ursprungligen skyddades genom att ställa in`ProtectedForForms` motsvarande egendom`Section` invända mot`false`. Detta tillåter användare att redigera innehållet i det specifika avsnittet utan några begränsningar.

#### F: Vilka skyddstyper kan tillämpas på ett Word-dokument?

S: Aspose.Words för .NET tillhandahåller olika skyddstyper som kan tillämpas på ett Word-dokument, inklusive:
- NoProtection: Inget skydd tillämpas.
- AllowOnlyRevisions: Användare kan bara göra ändringar av dokumentet.
- AllowOnlyComments: Användare kan bara lägga till kommentarer till dokumentet.
- AllowOnlyFormFields: Användare kan bara redigera formulärfält i dokumentet.
- ReadOnly: Dokumentet är skrivskyddat och ingen redigering är tillåten.


