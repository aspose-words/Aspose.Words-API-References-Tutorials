---
title: Ställ in teckensnittsmappsystem och anpassad mapp
linktitle: Ställ in teckensnittsmappsystem och anpassad mapp
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ställa in system- och anpassade teckensnittsmappar när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

den här handledningen går vi igenom steg-för-steg-processen för att ställa in systemfontmappar och en anpassad mapp när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av den här handledningen kommer du att veta hur du anger flera teckensnittsmappar, inklusive systemmappen och en anpassad mapp, som ska användas när du renderar dina dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade renderade dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet för att rendera
 Sedan kan du ladda dokumentet för att rendera med hjälp av`Document` klass. Var noga med att ange rätt dokumentsökväg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 3: Ställ in system- och anpassade teckensnittsmappar
 Nu kan du ställa in systemfontmappar och en anpassad mapp med hjälp av`FontSettings` klass och`SetFontsSources()` metod. Först måste du hämta listan över miljöberoende teckensnittskällor som använder`GetFontsSources()` och lagra den i en lista. Sedan kan du skapa en ny instans av`FolderFontSource` ange sökvägen till den anpassade mappen som innehåller dina teckensnitt. Lägg till den här instansen i listan över befintliga teckensnittskällor. Slutligen, använd`SetFontsSources()` för att uppdatera teckensnittskällorna med den nya listan.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Steg 4: Använd teckensnittsinställningar
 Därefter måste du tillämpa teckensnittsinställningarna på ditt dokument med hjälp av`FontSettings` egendom av`Document` klass.

```csharp
doc.FontSettings = fontSettings;
```

## Steg 5: Spara det renderade dokumentet
Slutligen kan du spara det renderade dokumentet till en fil genom att

   använda`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Exempel på källkod för Set Fonts Folders System och Custom Folder med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Hämta mängden miljöberoende teckensnittskällor som söks efter som standard.
// Till exempel kommer detta att innehålla en "Windows\Fonts\"-källa på en Windows-dator.
// Vi lägger till den här arrayen i en ny lista för att göra det mycket lättare att lägga till eller ta bort teckensnittsposter.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Lägg till en ny mappkälla som instruerar Aspose.Words att söka efter typsnitt i följande mapp.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Lägg till den anpassade mappen som innehåller våra typsnitt till listan över befintliga teckensnittskällor.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in systemfontmappar och en anpassad mapp när man renderar ett dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt ange flera teckensnittsmappar, inklusive systemmappen och en anpassad mapp, som ska användas när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för ordbehandling med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa teckensnittskällorna som används när du renderar dina dokument efter dina specifika behov.

### FAQ's

#### F: Hur kan jag ställa in systemfontmappar i Aspose.Words?

S: För att ställa in systemfontmappar i Aspose.Words behöver du inte göra någonting. Aspose.Words använder automatiskt systemteckensnitt som är installerade på ditt operativsystem.

#### F: Hur kan jag ställa in anpassade teckensnittsmappar i Aspose.Words?

 S: För att ställa in de anpassade teckensnittsmapparna i Aspose.Words kan du använda`SetFontsFolders` metod för`Fonts` klass som anger platserna för de anpassade teckensnittsmapparna.

#### F: Kan jag ange flera anpassade teckensnittsmappar i Aspose.Words?

 S: Ja, du kan ange flera anpassade teckensnittsmappar i Aspose.Words med hjälp av`SetFontsFolders` metod för`Fonts` klass med en lista över mappplatser.

#### F: Hur kan jag kontrollera teckensnittsmapparna som definieras i Aspose.Words?

 För att kontrollera teckensnittsmapparna som definieras i Aspose.Words kan du använda`GetFolders` metod för`Fonts` klass för att få listan över konfigurerade teckensnittsmappar.

#### F: Har anpassade mappteckensnitt prioritet framför systemteckensnitt i Aspose.Words?

S: Ja, anpassade mappteckensnitt har prioritet framför systemteckensnitt i Aspose.Words. Om ett teckensnitt finns i både anpassade mappar och systemteckensnitt, kommer Aspose.Words att använda versionen från den anpassade mappen.