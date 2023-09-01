---
title: Uppdatera senast utskrivna egenskap i PDF-dokument
linktitle: Uppdatera senast utskrivna egenskap i PDF-dokument
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att uppdatera egenskapen "Senast utskriven" vid konvertering till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder egenskapen "Sista utskrift" i PDF-dokumentuppdateringsfunktionen med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av den här handledningen kommer du att kunna förstå hur du konfigurerar alternativet att uppdatera egenskapen "Senast utskrivet" när du konverterar till PDF.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "Rendering.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 3: Konfigurera Spara som PDF-alternativ med den uppdaterade egenskapen "Senast utskriven".

 För att möjliggöra uppdatering av egenskapen "Senast utskriven" vid konvertering till PDF, måste vi konfigurera`PdfSaveOptions` objekt och ställ in`UpdateLastPrintedProperty` egendom till`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Steg 4: Spara dokumentet som en PDF med uppdateringen av egenskapen "Senast utskriven".

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt aktiverat uppdatering av egenskapen "Senast utskriven" när du konverterade ett dokument till PDF med Aspose.Words för .NET.

### Exempel på källkod för uppdatering av egenskapen "Senast utskriven" med Aspose.Words för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Slutsats

I den här handledningen förklarade vi hur man uppdaterar egenskapen "Sista utskrivna" i ett PDF-dokument med Aspose.Words för .NET. Genom att följa de givna stegen kan du enkelt konfigurera alternativet att uppdatera egenskapen "Senast utskrivet" när du konverterar ett dokument till PDF. Använd den här funktionen för att hålla reda på dokumentanvändning och relaterad information.

### Vanliga frågor

#### F: Vad är egenskapen "Senast utskriven" i ett PDF-dokument?
S: Egenskapen "Senast utskriven" i ett PDF-dokument hänvisar till datum och tid då dokumentet senast skrevs ut. Den här egenskapen kan vara användbar för att spåra information om dokumentanvändning och hantering.

#### F: Hur kan jag uppdatera egenskapen "Last Printed" i ett PDF-dokument med Aspose.Words for .NET?
S: För att uppdatera egenskapen "Last Printed" i ett PDF-dokument med Aspose.Words for .NET, följ dessa steg:

 Skapa en instans av`Document` klass som anger sökvägen till Word-dokumentet.

 Skapa en instans av`PdfSaveOptions` klass och ställ in`UpdateLastPrintedProperty` egendom till`true` för att möjliggöra uppdatering av egenskapen "Senast utskriven".

 Använd`Save` metod för`Document`klass för att spara dokumentet i PDF-format genom att ange sparalternativ.

#### F: Hur kan jag kontrollera om egenskapen "Senast utskriven" har uppdaterats i det genererade PDF-dokumentet?
S: Du kan kontrollera om egenskapen "Senast utskriven" har uppdaterats i det genererade PDF-dokumentet genom att öppna PDF-filen med en kompatibel PDF-läsare, som Adobe Acrobat Reader, och visa dokumentinformationen. Datum och tid för den senaste utskriften ska motsvara datum och tid för genereringen av PDF-dokumentet.
