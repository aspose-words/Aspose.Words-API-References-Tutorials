---
title: Konvertera metafiler till svg
linktitle: Konvertera metafiler till svg
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att konvertera metafiler till SVG-format när du konverterar ett dokument till HTML med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

I den här handledningen går vi igenom C#-källkoden för att konvertera metafiler till SVG-format med Aspose.Words för .NET. Denna funktion låter dig konvertera metafiler till SVG-format när du konverterar ett dokument till HTML.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Infoga en SVG-bild i dokumentet

det här steget kommer vi att infoga en SVG-bild i dokumentet som ska konverteras. Använd följande kod för att infoga en SVG-bild med en HTML-tagg:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Denna kod skapar en instans av`Document` och`DocumentBuilder` att bygga dokumentet. Den infogar en`<svg>` tagg som innehåller en`<polygon>` element med attribut för att definiera formen och stilen för SVG-bilden.

## Steg 3: Ställ in HTML-sparalternativ

Nu ställer vi in HTML-sparalternativen och anger att metafiler ska konverteras till SVG-format. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Denna kod skapar en instans av`HtmlSaveOptions` och uppsättningar`MetafileFormat` till`HtmlMetafileFormat.Svg` för att ange att metafiler ska konverteras till SVG-format vid konvertering till HTML.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av HTML-sparalternativen som definierats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Denna kod konverterar dokumentet till HTML och sparar det till en fil med metafilerna konverterade till SVG.

### Exempel på källkod för Convert Metafiler till Svg med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
