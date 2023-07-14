---
title: Ange standardteckensnitt vid rendering
linktitle: Ange standardteckensnitt vid rendering
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ange standardteckensnittet när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/specify-default-font-when-rendering/
---

den här handledningen går vi igenom steg-för-steg-processen för att ange standardteckensnittet när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av den här handledningen kommer du att veta hur du anger ett standardteckensnitt som ska användas när du renderar dina dokument med Aspose.Words för .NET.

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

## Steg 3: Ställ in standardteckensnitt
 Nu kan du ange vilket standardteckensnitt som ska användas vid rendering genom att skapa en instans av`FontSettings` klass och ställa in`DefaultFontName`egendom av`DefaultFontSubstitution` invända mot`DefaultFontSubstitution` objekt`SubstitutionSettings` av`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Steg 4: Spara det renderade dokumentet
 Slutligen kan du spara det renderade dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Exempel på källkod för Specificera standardteckensnitt vid rendering med Aspose.Words för .NET 

```csharp
//Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Om standardteckensnittet som definieras här inte kan hittas under renderingen då
// det närmaste typsnittet på maskinen används istället.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Slutsats
den här handledningen lärde vi oss hur man anger standardteckensnittet när man renderar ett dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt ställa in ett standardteckensnitt som ska användas när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för ordbehandling med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa renderingen av dina dokument efter dina specifika behov.

### FAQ's

#### F: Hur kan jag ange ett standardteckensnitt när jag konverterar till PDF i Aspose.Words?

 S: För att ange ett standardteckensnitt när du konverterar till PDF i Aspose.Words kan du använda`PdfOptions`klass och ställ in`DefaultFontName` egenskap till namnet på det önskade teckensnittet.

#### F: Vad händer om standardteckensnittet inte är tillgängligt vid konvertering till PDF?

S: Om det angivna standardteckensnittet inte är tillgängligt vid konvertering till PDF, kommer Aspose.Words att använda ett ersättningsteckensnitt för att visa texten i det konverterade dokumentet. Detta kan orsaka en liten skillnad i utseende från det ursprungliga teckensnittet.

#### F: Kan jag ange ett standardteckensnitt för andra utdataformat, som DOCX eller HTML?

S: Ja, du kan ange ett standardteckensnitt för andra utdataformat som DOCX eller HTML genom att använda lämpliga konverteringsalternativ och ställa in motsvarande egenskap för varje format.

#### F: Hur kan jag kontrollera standardteckensnittet som anges i Aspose.Words?

 S: För att kontrollera standardteckensnittet som anges i Aspose.Words, kan du använda`DefaultFontName`egendom av`PdfOptions` klass och hämta namnet på det konfigurerade teckensnittet.

#### F: Är det möjligt att ange olika standardteckensnitt för varje del av dokumentet?

S: Ja, det är möjligt att ange olika standardteckensnitt för varje avsnitt av dokumentet med hjälp av formateringsalternativ som är specifika för varje avsnitt. Detta skulle dock kräva mer avancerad manipulering av dokumentet med Aspose.Words-funktioner.