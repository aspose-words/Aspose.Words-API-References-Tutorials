---
title: Obegränsad sektion
linktitle: Obegränsad sektion
second_title: Aspose.Words för .NET API Referens
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

Slutligen, spara det ändrade dokumentet:

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

// Som standard är alla avsnitt skyddade, men vi kan selektivt stänga av skyddet.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Genom att följa dessa steg kommer du enkelt att kunna definiera obegränsade avsnitt i ditt Word-dokument med Aspose.Words för .NET.

