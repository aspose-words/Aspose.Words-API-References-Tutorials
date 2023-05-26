---
title: Exportera resurser
linktitle: Exportera resurser
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att exportera dokumentresurser när du sparar som HTML med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/export-resources/
---

I den här handledningen går vi igenom C#-källkoden för att exportera dokumentresurser med Aspose.Words för .NET. Den här funktionen låter dig exportera resurser, som typsnitt, som externa filer när du sparar ett dokument i HTML-format.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda dokumentet för att exportera. Använd följande kod för att ladda dokumentet från en angiven katalog:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Denna kod skapar en instans av`Document` genom att ladda dokumentet från den angivna katalogen.

## Steg 3: Konfigurera alternativ för HTML-säkerhetskopiering

Nu kommer vi att konfigurera HTML-sparalternativen för att exportera dokumentresurserna. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resurser"
};
```

 Denna kod skapar en instans av`HtmlSaveOptions` och ställer in följande alternativ:

- `CssStyleSheetType` är satt till`CssStyleSheetType.External`för att exportera CSS-formatmallen till en extern fil.
- `ExportFontResources` är satt till`true` för att exportera teckensnittsresurser.
- `ResourceFolder` anger destinationskatalogen där resurserna ska sparas.
- `ResourceFolderAlias` anger URL-aliaset som kommer att användas för att komma åt resurser.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av de HTML-sparalternativ som konfigurerats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Den här koden konverterar dokumentet till HTML och sparar resurserna i den angivna katalogen med det angivna URL-aliaset.

### Exempel på källkod för Export Resources med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resurser"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Var noga med att ange rätt sökväg till dokumentkatalogen i`dataDir` variabel.