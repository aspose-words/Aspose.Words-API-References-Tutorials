---
title: Ställ in True Type Fonts-mappen
linktitle: Ställ in True Type Fonts-mappen
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att ställa in mappen True Type fonts när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-true-type-fonts-folder/
---

den här handledningen går vi igenom steg-för-steg-processen för att ställa in mappen True Type fonts när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du anger en anpassad mapp som innehåller True Type-teckensnitt som ska användas när du renderar dina dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade renderade dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet för att rendera
 Därefter måste du ladda dokumentet för att rendera med hjälp av`Document` klass. Var noga med att ange rätt dokumentsökväg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 3: Ställ in True Type Fonts-mappen
 Nu kan du ange mappen med True Type-teckensnitt som ska användas vid rendering genom att skapa en instans av`FontSettings` klass och använda`SetFontsFolder()` metod för att ställa in teckensnittsmappen. Du kan ange en anpassad mapp som innehåller dina True Type-teckensnitt. Den andra parametern till`SetFontsFolder()` anger om du vill söka i undermappar till den angivna mappen också.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Steg 4: Spara det renderade dokumentet
 Slutligen kan du spara det renderade dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Exempel på källkod för Set True Type Fonts Folder med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Observera att den här inställningen åsidosätter alla standardfontkällor som söks efter som standard. Nu kommer endast dessa mappar att sökas efter
	// Teckensnitt vid rendering eller inbäddning av teckensnitt. För att lägga till en extra teckensnittskälla samtidigt som systemets teckensnittskällor behålls, använd sedan både FontSettings.GetFontSources och
	// FontSettings.SetFontSources istället
	fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
	// Ställ in teckensnittsinställningar
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in mappen true type fonts när man renderar ett dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt ange en anpassad mapp som innehåller True Type-teckensnitt som ska användas när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att arbeta med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa typsnitten som används när du renderar dina dokument efter dina specifika behov.