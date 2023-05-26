---
title: Ställ in teckensnittsmappar
linktitle: Ställ in teckensnittsmappar
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att ställa in teckensnittsmappar när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-fonts-folders/
---

den här handledningen går vi igenom steg-för-steg-processen för att ställa in teckensnittsmappar när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du anger typsnittsmappar som ska användas när du renderar dina dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade renderade dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ställ in teckensnittskällor
 Sedan kan du ställa in teckensnittskällorna med hjälp av`FontSettings.DefaultInstance` klass och`SetFontsSources()` metod. I det här exemplet använder vi både en systemfontkälla och en anpassad mappteckensnittskälla. Var noga med att justera sökvägen till mappen för anpassade teckensnitt enligt dina behov.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Steg 3: Ladda dokumentet för att rendera
 Nu kan du ladda dokumentet för att rendera med hjälp av`Document` klass. Var noga med att ange rätt dokumentsökväg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 4: Spara det renderade dokumentet
 Slutligen kan du spara det renderade dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Exempel på källkod för Set Fonts-mappar med Aspose.Words för .NET 
```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in teckensnittsmappar när man renderar ett dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt ange vilka teckensnittskällor som ska användas när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att arbeta med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa teckensnittskällorna som används när du renderar dina dokument efter dina specifika behov.