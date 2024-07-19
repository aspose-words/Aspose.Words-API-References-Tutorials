---
title: Exportera id-adresser för Mhtml-resurser
linktitle: Exportera id-adresser för Mhtml-resurser
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att exportera CID-URLer för MHTML-resurser när du sparar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

I den här handledningen går vi igenom C#-källkoden för att exportera CID-URL:er för MHTML-resurser med Aspose.Words för .NET. Denna funktion låter dig exportera CID-URL:er för MHTML-resurser när du sparar ett dokument i MHTML-format.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda dokumentet för att exportera. Använd följande kod för att ladda dokumentet från en angiven katalog:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Denna kod skapar en instans av`Document` genom att ladda dokumentet från den angivna katalogen.

## Steg 3: Konfigurera alternativ för HTML-säkerhetskopiering

Nu kommer vi att konfigurera HTML-sparalternativ för att exportera CID-URL:er för MHTML-resurser. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Denna kod skapar en instans av`HtmlSaveOptions` med sparaformatet inställt på MHTML. Det möjliggör också export av CID-URL:er för MHTML-resurser genom inställning`ExportCidUrlsForMhtmlResources` till`true`.

## Steg 4: Konvertera och spara dokumentet till MHTML

Slutligen kommer vi att konvertera dokumentet till MHTML med hjälp av HTML-sparalternativen som konfigurerats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Denna kod konverterar dokumentet till MHTML och sparar det till en fil med CID-adresserna för de exporterade MHTML-resurserna.

### Exempel på källkod för Export Cid-urls för Mhtml-resurser med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Var noga med att ange rätt sökväg till dokumentkatalogen i`dataDir` variabel.

Du har nu lärt dig hur du exporterar CID-URL:er för MHTML-resurser när du sparar ett dokument i MHTML-format med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt hantera CID-adresser i dina exporterade MHTML-dokument.

