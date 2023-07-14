---
title: Dokument sidinställningar
linktitle: Dokument sidinställningar
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att sätta upp en dokumentlayout med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/document-page-setup/
---

I den här handledningen går vi igenom C#-källkoden för att konfigurera dokumentlayouten med Aspose.Words för .NET. Denna funktion låter dig ställa in layoutläget, antalet tecken per rad och antalet rader per sida.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som vi vill konfigurera. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Konfigurera layouten

Låt oss nu konfigurera dokumentlayouten. Använd följande kod för att ställa in layoutläge, antal tecken per rad och antal rader per sida:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Denna kod ställer in layoutläget på "Grid" och anger sedan antalet tecken per rad och antalet rader per sida.

### Exempel på källkod för Document Page Setup med Aspose.Words för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Ställ in layoutläget för en sektion som gör det möjligt att definiera dokumentrutnätets beteende.
	// Observera att fliken Document Grid blir synlig i dialogrutan Utskriftsformat i MS Word
	// om något asiatiskt språk definieras som redigeringsspråk.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du konfigurerar layouten för ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt anpassa layouten för dina egna dokument.