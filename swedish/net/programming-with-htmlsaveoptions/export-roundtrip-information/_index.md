---
title: Exportera information om tur och retur
linktitle: Exportera information om tur och retur
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att exportera information tur och retur när du sparar ett dokument som HTML med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

I den här handledningen går vi igenom C#-källkoden för att exportera information om tur och retur från ett dokument med Aspose.Words för .NET. Denna funktion låter dig inkludera information tur och retur i den exporterade HTML-filen, vilket gör det lättare att hämta ändringar som gjorts i originaldokumentet.

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

Nu kommer vi att konfigurera HTML-sparalternativen för att exportera dokumentets information om tur och retur. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Denna kod skapar en instans av`HtmlSaveOptions`och ställer in`ExportRoundtripInformation` möjlighet att`true` att inkludera information tur och retur vid export.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av de HTML-sparalternativ som konfigurerats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Den här koden konverterar dokumentet till HTML inklusive informationen tur och retur och sparar den exporterade HTML-filen i den angivna katalogen.

### Exempel på källkod för export av information om tur och retur med Aspose.Words för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Var noga med att ange rätt sökväg till dokumentkatalogen i`dataDir` variabel.