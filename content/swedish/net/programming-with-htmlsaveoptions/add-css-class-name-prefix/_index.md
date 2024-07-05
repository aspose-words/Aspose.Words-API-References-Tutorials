---
title: Lägg till Css Class Name Prefix
linktitle: Lägg till Css Class Name Prefix
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att lägga till ett CSS-klassnamnsprefix när du konverterar ett dokument till HTML med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

I den här handledningen går vi igenom C#-källkoden för att lägga till ett CSS-klassnamnsprefix med Aspose.Words för .NET. Den här funktionen låter dig lägga till ett anpassat prefix till genererade CSS-klassnamn när du konverterar ett dokument till HTML.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som vi vill konvertera till HTML. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Ställ in HTML-sparalternativ

Låt oss nu ställa in HTML-sparalternativ, inklusive CSS-formatmallstyp och CSS-klassnamnsprefix. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Denna kod skapar en instans av`HtmlSaveOptions` och uppsättningar`CssStyleSheetType` till`CssStyleSheetType.External`för att generera en extern CSS-stilmall, och`CssClassNamePrefix` till`"pfx_"` till prefix`"pfx_"` att namnge CSS-klass.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av HTML-sparalternativen som definierats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Denna kod konverterar dokumentet till HTML och sparar det till en fil med CSS-klassnamnsprefixet tillagt.

### Exempel på källkod för Add Css Class Name Prefix med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du lägger till ett CSS-klassnamnsprefix när du konverterar ett dokument till HTML med Aspose.Words för .NET. Genom att följa steg-för-steg-guidesteget i denna handledning kan du anpassa CSS-klassnamnen i dina konverterade HTML-dokument.