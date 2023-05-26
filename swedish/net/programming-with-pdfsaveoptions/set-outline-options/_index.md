---
title: Ställ in dispositionsalternativ
linktitle: Ställ in dispositionsalternativ
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att ställa in dispositionsalternativ i ett PDF-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/set-outline-options/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för inställning av konturalternativ till metafilstorlek med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du ställer in dispositionsalternativ i ett dokument och genererar en PDF med motsvarande dispositionsalternativ.

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

## Steg 3: Konfigurera spara som PDF-alternativ med planalternativ

 För att ställa in dispositionsalternativ i den genererade PDF-filen måste vi konfigurera`PdfSaveOptions` objekt. Vi kan ställa in antalet rubriknivåer (`HeadingsOutlineLevels`) och antalet utökade dispositionsnivåer (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Steg 4: Spara dokument som PDF med dispositionsalternativ

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt angett dispositionsalternativ i ett dokument och genererat en PDF med motsvarande dispositionsalternativ med Aspose.Words för .NET.

### Exempel på källkod för att ställa in planalternativ till metafilstorlek med Aspose.Words för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```
