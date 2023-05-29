---
title: Ta bort fält
linktitle: Ta bort fält
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att ta bort sammanslagningsfält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/delete-fields/
---

För att förklara hur man använder funktionen "Ta bort fält" i Aspose. Ord för .NET vi har skapat en steg för steg guide nedan. 

Det är viktigt att följa varje steg noga för att uppnå önskat resultat. 

## Steg 1: Skapa ett nytt dokument

I det här kodavsnittet börjar vi med att skapa ett nytt tomt dokument med följande rad: 

```csharp
Document doc = new Document();
```

## Steg 2: Ta bort sammanslagningsfält

 För att ta bort alla sammanslagningsfält som finns i dokumentet använder vi`DeleteFields()` fungera. 

Detta är särskilt användbart om du bara vill behålla det statiska innehållet och ta bort all sammanfogningsinformation. 

### Källkodsexempel för Ta bort fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda befintligt dokument.
Document doc = new Document(dataDir + "YourDocument.docx");

// Ta bort sammanslagningsfält.
doc.MailMerge.DeleteFields();

// Spara det ändrade dokumentet.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 I vårt exempel laddar vi först ett befintligt dokument innan vi ringer`DeleteFields()`. Slutligen sparar vi det ändrade dokumentet med ett nytt filnamn. 

För att effektivt ta bort sammanslagna fält från ett dokument med Aspose.Words för .NET:s "Ta bort fält"-funktion, ta en cue från detta exempel. 

Kom alltid ihåg att ersätta "DIN DOKUMENTKATOGRAF" med din specifika katalogsökväg. 

Vår guide för implementering av "Delete Fields"-funktionaliteten genom Aspose.Words för .NET har därmed avslutats.