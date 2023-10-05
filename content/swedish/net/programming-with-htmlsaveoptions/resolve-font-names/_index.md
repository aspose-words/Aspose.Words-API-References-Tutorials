---
title: Lös teckensnittsnamn
linktitle: Lös teckensnittsnamn
second_title: Aspose.Words Document Processing API
description: Steg-för-steg guide för att lösa saknade teckensnittsnamn vid konvertering till HTML med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/resolve-font-names/
---

I den här handledningen går vi igenom C#-källkoden för att lösa saknade teckensnittsnamn med Aspose.Words för .NET. Med den här funktionen kan du automatiskt lösa saknade teckensnittsnamn när du konverterar ett dokument till HTML.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I detta steg kommer vi att ladda dokumentet som ska behandlas. Använd följande kod för att ladda dokumentet från en angiven katalog:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Denna kod skapar en instans av`Document` genom att ladda dokumentet från den angivna katalogen.

## Steg 3: Konfigurera alternativ för HTML-säkerhetskopiering

Nu kommer vi att konfigurera HTML-sparalternativ för att lösa saknade teckensnittsnamn under konvertering. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Denna kod skapar en instans av`HtmlSaveOptions`och ställer in`ResolveFontNames` möjlighet att`true`för att lösa saknade teckensnittsnamn vid konvertering till HTML. Även`PrettyFormat` alternativet är inställt på`true` för att få snyggt formaterad HTML-kod.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av de HTML-sparalternativ som konfigurerats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Denna kod konverterar dokumentet till HTML genom att automatiskt lösa saknade teckensnittsnamn och sparar den konverterade HTML-filen i den angivna katalogen.

### Exempel på källkod för Resolve Font Names med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Var noga med att ange rätt sökväg till dokumentkatalogen i`dataDir` variabel.