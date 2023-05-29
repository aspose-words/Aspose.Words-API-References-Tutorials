---
title: Ladda avstavningsordbok för språk
linktitle: Ladda avstavningsordbok för språk
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du laddar en avstavningsordbok för ett specifikt språk i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

denna steg-för-steg handledning visar vi dig hur du laddar en avstavningsordlista för ett specifikt språk till Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

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

Spara slutligen det ändrade dokumentet:

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