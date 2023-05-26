---
title: Obegränsade redigerbara regioner
linktitle: Obegränsade redigerbara regioner
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar obegränsade redigerbara områden i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/unrestricted-editable-regions/
---

den här handledningen guidar vi dig genom stegen för att använda funktionen för obegränsade redigerbara områden i Aspose.Words för .NET. Den här funktionen låter dig definiera områden i ett Word-dokument där innehåll kan redigeras utan begränsningar, även om resten av dokumentet är skrivskyddat. Följ stegen nedan:

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


