---
title: Konvertera metafiler till emf eller wmf
linktitle: Konvertera metafiler till emf eller wmf
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att konvertera metafiler till EMF- eller WMF-format vid konvertering av ett dokument till HTML med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

den här handledningen går vi igenom C#-källkoden för att konvertera metafiler till EMF- eller WMF-format med Aspose.Words för .NET. Den här funktionen låter dig konvertera bilder i metafilformat till mer kompatibla format som EMF eller WMF när du konverterar ett dokument till HTML.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Infoga en bild i dokumentet

I det här steget kommer vi att infoga en bild i dokumentet som ska konverteras. Använd följande kod för att infoga en bild från en datakälla med en HTML-tagg:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Denna kod skapar en instans av`Document` och`DocumentBuilder` att bygga dokumentet. Den infogar en`<img>` tagga in i dokumentet med en base64-kodad bild.

## Steg 3: Ställ in HTML-sparalternativ

Nu ställer vi in HTML-sparalternativen, inklusive metafilformatet som ska användas för bilder. Använd följande kod:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Denna kod skapar en instans av`HtmlSaveOptions` och uppsättningar`MetafileFormat` till`HtmlMetafileFormat.EmfOrWmf` för att ange att metafiler ska konverteras till EMF- eller WMF-format vid konvertering till HTML.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av spara HTML-alternativen som tidigare definierats. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Den här koden konverterar dokumentet till HTML och sparar det till en fil med de konverterade metafilerna i EMF- eller WMF-format beroende på de sparade alternativen.

### Exempel på källkod för konvertera metafiler till emf eller wmf med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Var noga med att ange rätt sökväg till dokumentkatalogen i`dataDir` variabel.

Du har nu lärt dig hur du konverterar metafiler till EMF- eller WMF-format när du konverterar ett dokument till HTML med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt hantera metafiler i dina konverterade HTML-dokument.