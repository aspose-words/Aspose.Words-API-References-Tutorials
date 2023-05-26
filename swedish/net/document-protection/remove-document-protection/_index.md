---
title: Ta bort dokumentskydd
linktitle: Ta bort dokumentskydd
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du tar bort skyddet från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/remove-document-protection/
---

den här handledningen kommer vi att guida dig genom stegen för att använda funktionen för att avskydda dokument i Aspose.Words för .NET. Den här funktionen låter dig ta bort skyddet från ett Word-dokument för att göra det tillgängligt för ytterligare redigering. Följ stegen nedan:

## Steg 1: Skapa dokumentet och lägga till innehåll

Börja med att skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Lägg till innehåll i dokumentet

Använd DocumentBuilder-objektet för att lägga till innehåll i dokumentet:

```csharp
builder.Writeln("Text added to a document.");
```

## Steg 3: Ta bort skyddet av dokument

För att avskydda dokumentet kan du använda metoden Unprotect() för Document-objektet. Du kan välja att ta bort skyddet utan lösenord eller med korrekt lösenord. Ta bort lösenordslöst skydd:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Se till att ersätta "newPassword" med rätt dokumentlösenord.

## Steg 4: Spara dokumentet utan skydd

Spara slutligen dokumentet oskyddat med hjälp av metoden Save() för Document-objektet:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara dokumentet oskyddat.

### Exempel på källkod för Remove Document Protection med Aspose.Words för .NET

Här är den fullständiga källkoden för att avskydda dokumentet med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	// Dokument kan ta bort skydd antingen utan lösenord eller med rätt lösenord.
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Genom att följa dessa steg kan du enkelt ta bort skyddet från Word-dokument med Aspose.Words för .NET.
