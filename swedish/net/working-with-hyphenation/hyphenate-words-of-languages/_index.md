---
title: Avstava ord av språk
linktitle: Avstava ord av språk
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du avstavar ord på olika språk i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-hyphenation/hyphenate-words-of-languages/
---

denna steg-för-steg handledning kommer vi att guida dig om hur du avstavar ord på olika språk i Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt källdokument som innehåller text på olika språk:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Steg 2: Spara avstavningsordböcker

Spara sedan avstavningsordböckerna för de olika språken du vill bearbeta. I det här exemplet registrerar vi ordböcker för amerikansk engelska och schweizertyska:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Se till att du har rätt ordboksfiler i din datakatalog.

## Steg 3: Bearbeta ord genom avstavning

 Nu kan du använda avstavningsfunktioner för att bearbeta ord på olika språk. Du kan använda olika metoder`Document` eller`DocumentBuilder`beroende på dina specifika behov.

```csharp
// Exempel: Använda avstavningsmetoden i DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Steg 4: Spara dokumentet

Spara slutligen det ändrade dokumentet:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Så ! Du har framgångsrikt bearbetat ord genom att avstava dem på olika språk i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för ordavstavning med Aspose.Words för .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Använd gärna den här koden i dina egna projekt och modifiera den för att passa dina specifika behov.
