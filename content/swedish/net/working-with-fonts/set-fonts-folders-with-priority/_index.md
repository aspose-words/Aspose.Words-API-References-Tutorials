---
title: Ställ in typsnittsmappar med prioritet
linktitle: Ställ in typsnittsmappar med prioritet
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ställa in teckensnittsmappar med prioritet när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-fonts-folders-with-priority/
---

I den här handledningen går vi igenom steg-för-steg-processen för att ställa in teckensnittsmappar med prioritet när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du anger flera teckensnittsmappar med anpassad sökprioritet när du renderar dina dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade renderade dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ställ in teckensnittsmappar med prioritet
 Sedan kan du ställa in teckensnittsmapparna med prioritet med hjälp av`FontSettings` klass och`SetFontsSources()`metod. Du kan ange flera teckensnittskällor med hjälp av instanser av`SystemFontSource`och`FolderFontSource`. I det här exemplet har vi definierat två teckensnittskällor: standardsystemets teckensnittskälla och en anpassad teckensnittsmapp med prioritet 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
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
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Exempel på källkod för Set Fonts-mappar med prioritet med Aspose.Words för .NET 
```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in teckensnittsmappar med prioritet när man renderar ett dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt ange flera teckensnittsmappar med anpassad sökprioritet när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för ordbehandling med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa teckensnittskällorna som används när du renderar dina dokument efter dina specifika behov.

### FAQ's

#### F: Hur kan jag ställa in teckensnittsmappar med prioritet i Aspose.Words?

 S: För att ställa in teckensnittsmappar med prioritet i Aspose.Words kan du använda`SetFontsFoldersWithPriority` metod för`Fonts` klass genom att ange placeringen av teckensnittsmapparna och deras prioritetsordning.

#### F: Vad händer om ett teckensnitt finns i flera mappar med olika prioritet?

S: Om ett teckensnitt finns i flera mappar med olika prioritet kommer Aspose.Words att använda versionen från mappen med högst prioritet vid bearbetning av dokument.

#### F: Kan jag ange flera teckensnittsmappar med samma prioritet i Aspose.Words?

S: Ja, du kan ange flera teckensnittsmappar med samma prioritet i Aspose.Words. Aspose.Words kommer att överväga dem alla med samma prioritet när de söker efter teckensnitt i dina dokument.

#### F: Hur kan jag kontrollera teckensnittsmapparna som definierats med prioritet i Aspose.Words?

 S: För att kontrollera teckensnittsmapparna som definieras med prioritet i Aspose.Words, kan du använda`GetFolders` metod för`Fonts` klass för att få listan över konfigurerade teckensnittsmappar inklusive deras prioritetsordning.

#### F: Vad är användningen för att ställa in teckensnittsmappar med prioritet i Aspose.Words?

S: Att ställa in teckensnittsmappar med prioritet i Aspose.Words låter dig styra sökordningen för teckensnitt i dina Word-dokument. Detta hjälper dig att säkerställa att de teckensnitt du vill använda används och undvika oönskade problem med teckensnittsersättning.