---
title: Lässkydd
linktitle: Lässkydd
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skyddar dina skrivskyddade Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/read-only-protection/
---
I den här handledningen guidar vi dig genom stegen för att använda skrivskyddsfunktionen i Aspose.Words för .NET. Med den här funktionen kan du göra ett Word-dokument skrivskyddat för att förhindra obehörig ändring. Följ stegen nedan:

## Steg 1: Skapa dokumentet och tillämpa skydd

Börja med att skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Skriv innehåll till dokumentet
Använd DocumentBuilder-objektet för att skriva innehåll till dokumentet:

```csharp
builder.Write("Open document as read-only");
```

## Steg 3: Ange lösenord och gör dokumentet skrivskyddat

Ställ in ett lösenord för dokumentet med egenskapen SetPassword() för WriteProtection-objektet:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Se till att ersätta "Mitt lösenord" med det faktiska lösenord du vill använda.

## Steg 4: Använd skrivskyddat dokument

Gör dokumentet skrivskyddat genom att ställa in egenskapen ReadOnlyRecommended till true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Steg 5: Använd skrivskyddat och spara dokumentet

Till sist, tillämpa skrivskyddat med metoden Protect() för Document-objektet:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara det skyddade dokumentet.

### Exempel på källkod för skrivskyddad användning av Aspose.Words för .NET

Här är den fullständiga källkoden för skrivskyddat skydd med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// Ange ett lösenord som är upp till 15 tecken långt.
	doc.WriteProtection.SetPassword("MyPassword");

	// Gör dokumentet som skrivskyddat.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Använd skrivskydd som skrivskyddat.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Genom att följa dessa steg kan du enkelt skydda dina dokument

