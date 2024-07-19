---
title: Avstava ord av språk
linktitle: Avstava ord av språk
second_title: Aspose.Words Document Processing API
description: Lär dig hur du avstavar ord på olika språk i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-hyphenation/hyphenate-words-of-languages/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du avstavar ord på olika språk i Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

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

Nu kan du använda avstavningsfunktioner för att bearbeta ord på olika språk. Du kan använda olika metoder`Document` eller`DocumentBuilder` beroende på dina specifika behov.

```csharp
// Exempel: Använda avstavningsmetoden i DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Steg 4: Spara dokumentet

Slutligen, spara det ändrade dokumentet:

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

### FAQ's

#### F: Hur kan jag syllabisera ett ord på ett specifikt språk med Aspose.Words?

 S: För att syllabisera ett ord på ett specifikt språk med Aspose.Words kan du använda`Hyphenation` klass och`Hyphenate()` metod. Skapa en instans av`Hyphenation` klass som anger det önskade språket, anropa sedan`Hyphenate()` metod som skickar ordet till stavning som ett argument. Detta ger dig stavelserna i ordet på det angivna språket.

#### F: Vilka språkkoder ska jag använda för att specificera stavningsspråket i Aspose.Words?

S: För att specificera språket i Aspose.Words måste du använda lämpliga språkkoder. Till exempel kan du använda "en" för engelska, "fr" för franska, "es" för spanska, "de" för tyska, etc. Se Aspose.Words-dokumentationen för en fullständig lista över språkkoder som stöds.

#### F: Fungerar stavning för alla språk i Aspose.Words?

S: Syllabisering i Aspose.Words beror på språkspecifika regler för syllabisering. Även om Aspose.Words stöder ett brett spektrum av språk, kanske vissa språk inte stöds eller så är stavning inte tillgänglig för dem. Kontrollera Aspose.Words-dokumentationen för att ta reda på vilka språk som stöds för syllabisering.