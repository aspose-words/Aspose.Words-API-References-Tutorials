---
title: Ställ in typsnittsmappar som standardinstans
linktitle: Ställ in typsnittsmappar som standardinstans
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att ställa in standardfontmappen när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-fonts-folders-default-instance/
---

I den här handledningen går vi igenom steg-för-steg-processen för att ställa in standardfontmappen när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du ställer in standardfontmappen som ska användas när du renderar dina dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade renderade dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ställ in standardfontmapp
Sedan kan du ställa in standardfontmappen med hjälp av`FontSettings.DefaultInstance` klass och`SetFontsFolder()` metod. Ange sökvägen till den typsnittsmapp du vill använda som standardmapp.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Steg 3: Ladda dokumentet för att rendera
 Nu kan du ladda dokumentet för att rendera med hjälp av`Document` klass. Var noga med att ange rätt dokumentsökväg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 4: Spara det renderade dokumentet
 Slutligen kan du spara det renderade dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Exempel på källkod för Set Fonts Folders Default Instance med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur du ställer in standardfontmappen när du renderar ett dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt ange vilken mapp med teckensnitt som ska användas som standardmapp när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att arbeta med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa teckensnittskällorna som används när du renderar dina dokument efter dina specifika behov.

### FAQ's

#### F: Hur kan jag ställa in standardfontmappar i Aspose.Words?

 S: För att ställa in standardtypsnittsmappar i Aspose.Words måste du använda`Fonts` klass och`SetFontsFolders` metod för att ange placeringar för anpassade teckensnittsmappar.

#### F: Påverkar inställningen av standardfontmappar alla Word-dokument som bearbetas med Aspose.Words?

S: Ja, inställning av standardtypsnittsmappar påverkar alla Word-dokument som bearbetas med Aspose.Words. När du har ställt in standardtypsnittsmapparna kommer Aspose.Words att använda dessa platser för att söka efter teckensnitt i alla dokument.

#### F: Kan jag ställa in flera standardfontmappar i Aspose.Words?

 S: Ja, du kan ställa in flera standardfontmappar i Aspose.Words. Du behöver bara ange platserna för anpassade teckensnittsmappar med hjälp av`SetFontsFolders` metod för`Fonts` klass.

#### F: Hur kan jag kontrollera standardfontmapparna som för närvarande är inställda i Aspose.Words?

 S: För att kontrollera standardfontmapparna som för närvarande är definierade i Aspose.Words, kan du använda`GetFolders` metod för`Fonts` klass för att få plats för de konfigurerade teckensnittsmapparna.

#### F: Kan jag använda anpassade teckensnitt i mina Word-dokument när jag ställer in standardmappar för teckensnitt?

S: Ja, genom att ställa in standardtypsnittsmappar kan du använda anpassade teckensnitt i dina Word-dokument. Du behöver bara placera typsnitten i de angivna mapparna och Aspose.Words kommer att använda dem när du genererar eller manipulerar dokumenten.