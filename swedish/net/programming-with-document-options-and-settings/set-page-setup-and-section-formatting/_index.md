---
title: Ställ in sidinställningar och avsnittsformatering
linktitle: Ställ in sidinställningar och avsnittsformatering
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att ställa in ett dokuments layout och sektionsformatering med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

I den här handledningen går vi igenom C#-källkoden för att ställa in layout och avsnittsformatering med Aspose.Words för .NET. Med den här funktionen kan du ställa in sidorientering, marginaler och pappersstorlek.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Skapa dokumentet

I det här steget skapar vi ett nytt dokument. Använd följande kod för att skapa dokumentet och initiera konstruktorn:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där du vill spara dokumentet.

## Steg 3: Konfigurera layouten och spara dokument

Låt oss nu konfigurera dokumentlayouten. Använd följande kod för att ställa in orientering, marginaler och pappersstorlek:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Den här koden ställer in sidorienteringen till liggande, vänstermarginalen till 50 och pappersstorleken till 10x14.

### Exempel på källkod för Set Page Setup och sektionsformatering med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Var noga med att ange rätt sökväg till katalogen där du vill spara dokumentet i`dataDir` variabel.

Du har nu lärt dig hur du konfigurerar layouten och sektionsformateringen av ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i den här handledningen kan du enkelt anpassa layouten och formateringen av dina egna dokument.