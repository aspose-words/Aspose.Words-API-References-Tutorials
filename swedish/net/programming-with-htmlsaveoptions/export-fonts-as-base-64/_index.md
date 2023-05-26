---
title: Exportera teckensnitt som bas 64
linktitle: Exportera teckensnitt som bas 64
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att exportera bas 64 teckensnitt när du sparar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

I den här handledningen går vi igenom C#-källkoden för att exportera bas 64-teckensnitt med Aspose.Words för .NET. Den här funktionen låter dig exportera teckensnitt som bas 64-data när du sparar ett dokument i HTML-format.

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

Nu kommer vi att konfigurera HTML-sparalternativen för att exportera bas 64-teckensnitt. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Denna kod skapar en instans av`HtmlSaveOptions` och uppsättningar`ExportFontsAsBase64` till`true` för att ange att typsnitt ska exporteras som bas 64-data när du sparar som HTML.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av de HTML-sparalternativ som konfigurerats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Denna kod konverterar dokumentet till HTML och sparar det till en fil med typsnitten exporterade som bas 64-data.

### Exempel på källkod för Export Fonts As Base 64 med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Var noga med att ange rätt sökväg till dokumentkatalogen i`dataDir` variabel.

Du har nu lärt dig hur du exporterar base 64-teckensnitt när du sparar ett dokument som HTML med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt exportera teckensnitt säkert och inbäddade i dina HTML-dokument.