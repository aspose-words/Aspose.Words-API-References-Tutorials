---
title: Ställ in dispositionsalternativ i ett PDF-dokument
linktitle: Ställ in dispositionsalternativ i ett PDF-dokument
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

## Slutsats

I den här handledningen förklarade vi hur man ställer in konturalternativ i ett PDF-dokument med Aspose.Words för .NET. Med hjälp av de beskrivna stegen kan du enkelt ange rubrik- och dispositionsnivåer i ditt dokument och generera en PDF-fil med motsvarande dispositionsalternativ. Njut av fördelarna med dispositionsalternativet för att förbättra struktur och navigering i dina PDF-dokument med Aspose.Words för .NET.

### Vanliga frågor

#### F: Vad är dispositionsalternativet i ett PDF-dokument?
S: Dispositionsalternativet i ett PDF-dokument hänvisar till den hierarkiska strukturen för dokumentinnehållet. Det låter dig skapa en interaktiv innehållsförteckning och underlättar navigeringen i dokumentet. Dispositionsalternativ bestämmer titel- och undertextnivåerna som ska inkluderas i dispositionen och detaljnivån som ska visas i den genererade dispositionen.

#### F: Hur kan jag ställa in dispositionsalternativ i ett PDF-dokument med Aspose.Words för .NET?
S: För att ställa in dispositionsalternativ i ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda dokumentet du vill konvertera till PDF med hjälp av`Document` klass och ange sökvägen till dokumentet i den angivna dokumentkatalogen.

 Konfigurera spara som PDF-alternativ genom att skapa en instans av`PdfSaveOptions` klass och använda`OutlineOptions` egenskap för att ställa in konturalternativen. Du kan ange antalet rubriknivåer som ska inkluderas i dispositionen med hjälp av`HeadingsOutlineLevels` egendom och antalet utökade dispositionsnivåer med hjälp av`ExpandedOutlineLevels` fast egendom.

 Spara dokumentet i PDF-format med hjälp av`Save` metod för`Document`klass som anger sökvägen och sparalternativ.

#### F: Vad är planalternativet för i ett PDF-dokument?
S: Dispositionsalternativet i ett PDF-dokument låter dig skapa en hierarkisk struktur av innehållet, vilket gör det lättare att navigera i dokumentet och komma åt olika avsnitt. Detta tillåter användare att snabbt hoppa till specifika delar av dokumentet genom att klicka på poster i innehållsförteckningen eller dispositionen. Konturalternativet förbättrar också läsupplevelsen genom att ge en översikt över dokumentstrukturen.
