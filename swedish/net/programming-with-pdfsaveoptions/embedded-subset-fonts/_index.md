---
title: Inbäddade delmängdsteckensnitt
linktitle: Inbäddade delmängdsteckensnitt
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att bädda in teckensnittsundergrupper i en PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för inbäddning av teckensnittsdelmängder med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av den här handledningen kommer du att kunna förstå hur du bäddar in delmängder av teckensnitt i ett dokument och genererar en PDF som endast innehåller de glyfer som används i dokumentet.

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

## Steg 3: Konfigurera spara som PDF-alternativ

 För att skapa en PDF-fil som endast innehåller de delmängder av teckensnitt som används i dokumentet måste vi konfigurera`PdfSaveOptions` objekt med`EmbedFullFonts` egenskapen inställd på`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Steg 4: Spara dokument som PDF med teckensnittsunderuppsättningar

 Slutligen kan vi spara dokumentet som en PDF med hjälp av teckensnittsunderuppsättningarna. Ange utdatafilens namn och`saveOptions` objekt som vi konfigurerade i föregående steg.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt bäddat in delmängder av teckensnitt i ett dokument och genererat en PDF som endast innehåller de glyfer som används i dokumentet med Aspose.Words för .NET.

### Exempel på källkod för att bädda in teckensnittsundergrupper med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Utdata-PDF-filen kommer att innehålla underuppsättningar av teckensnitten i dokumentet.
	// Endast de glyfer som används i dokumentet ingår i PDF-teckensnitten.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```
