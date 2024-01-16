---
title: Ladda avstavningsordbok för språk
linktitle: Ladda avstavningsordbok för språk
second_title: Aspose.Words Document Processing API
description: Lär dig hur du laddar en avstavningsordbok för ett specifikt språk i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

I denna steg-för-steg handledning visar vi dig hur du laddar en avstavningsordlista för ett specifikt språk till Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

 För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från[Aspose.Releases]https://releases.aspose.com/words/net/.

## Steg 1: Ladda dokumentet

Ladda först ditt dokument från den angivna katalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Steg 2: Laddar avstavningsordlistan

Öppna sedan en ström till avstavningsordboksfilen och spara den för önskat språk. I det här exemplet laddar vi en ordbok för schweizisk tyska (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Se till att du har rätt ordboksfil i din datakatalog.

## Steg 3: Spara det ändrade dokumentet

Slutligen, spara det ändrade dokumentet:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Så ! Du har framgångsrikt laddat en avstavningsordbok för ett specifikt språk i Aspose.Words för .NET.

### Exempel på källkod för laddning av avstavningsordbok för ett språk som använder Aspose.Words för .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Använd gärna den här koden i dina egna projekt och modifiera den för att passa dina specifika behov.

### FAQ's

#### F: Hur laddar man en syllabiseringsordbok för ett specifikt språk i Aspose.Words?

 S: För att ladda en stavningsordbok för ett specifikt språk i Aspose.Words kan du använda`Hyphenation` klass och`LoadDictionary()` metod. Skapa en instans av`Hyphenation` klass och ring`LoadDictionary()` metod som anger sökvägen till lexikonfilen för det önskade språket. Detta kommer att ladda syllabiseringsordboken i Aspose.Words.

#### F: Var kan jag hitta ordbokfiler för olika språk?

S: Du kan hitta ordbokfiler för olika språk på olika onlineresurser. Dessa filer är vanligtvis i XML- eller TEX-format. Du kan hitta lexikon för öppen källkod för olika språk på webbplatser dedikerade till lingvistiska projekt eller källkodsarkiv.

#### F: Hur kan jag tillämpa den inlästa stavelseordboken på ett dokument i Aspose.Words?

 S: För att tillämpa den laddade ordboken för stavning på ett dokument i Aspose.Words, måste du iterera över orden i dokumentet och använda`Hyphenate()` metod för`Hyphenation`klass för att få stavningen av orden. Du kan sedan formatera de stavelseordnade orden efter behov, till exempel genom att lägga till bindestreck mellan stavelserna.

#### F: Vilka språk stöds för stavning i Aspose.Words?

S: Aspose.Words stöder stavning för flera språk inklusive engelska, franska, spanska, tyska, italienska, holländska, ryska, portugisiska, svenska, norska, danska, finska, polska, tjeckiska och många fler. Se Aspose.Words-dokumentationen för den fullständiga listan över språk som stöds för stavning.