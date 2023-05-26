---
title: Ta bort skrivskyddad begränsning
linktitle: Ta bort skrivskyddad begränsning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du tar bort skrivskyddet från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/remove-read-only-restriction/
---
I den här handledningen kommer vi att leda dig genom stegen för att använda Aspose.Words for .NET skrivskyddad begränsningsborttagningsfunktion. Den här funktionen låter dig ta bort skrivskyddet från ett Word-dokument för att göra det redigerbart. Följ stegen nedan:

## Steg 1: Skapa dokumentet och ställa in skyddet

Börja med att skapa en instans av klassen Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Ställ in ett lösenord för dokumentet med egenskapen SetPassword() för WriteProtection-objektet:

Se till att ersätta "MyPassword" med det faktiska lösenordet du använde för att skydda dokumentet.

## Steg 2: Ta bort skrivskyddad begränsning

För att ta bort den skrivskyddade begränsningen, ställ in egenskapen ReadOnlyRecommended till false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Steg 3: Använd obegränsat skydd

Till sist, tillämpa obegränsat skydd med hjälp av Document-objektets Protect()-metod:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara dokumentet utan skrivskyddad begränsning.

### Exempel på källkod för Ta bort skrivskyddad begränsning med Aspose.Words för .NET

Här är den fullständiga källkoden för att ta bort den skrivskyddade begränsningen med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// Ange ett lösenord som är upp till 15 tecken långt.
	doc.WriteProtection.SetPassword("MyPassword");

	// Ta bort alternativet skrivskyddat.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Använd skrivskydd utan något skydd.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

Genom att följa dessa steg kan du enkelt ta bort den skrivskyddade begränsningen från ett Word-dokument med Aspose.Words för .NET.

