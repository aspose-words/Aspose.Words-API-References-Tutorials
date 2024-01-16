---
title: Ställ in fotnots- och slutnotposition
linktitle: Ställ in fotnots- och slutnotposition
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in positionen för fotnoter och slutnoter i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att ställa in fotnoters och slutnoters position i ett Word-dokument. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

 För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från[Aspose.Releases]https://releases.aspose.com/words/net/.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt källdokument:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Steg 2: Ställ in fotnots- och slutnotposition

 Gå sedan till`FootnoteOptions` och`EndnoteOptions` egenskaper för dokumentet för att ställa in positionen för fotnoter och slutnoter. I det här exemplet ställer vi in fotnoternas position under texten och positionen för slutnoter i slutet av avsnittet:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Steg 3: Spara dokumentet

Slutligen, spara det ändrade dokumentet:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Det är allt! Du har framgångsrikt angett positionen för fotnoter och slutnoter i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för Set Fotnot And Endnote Position med Aspose.Words för .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.

### FAQ's

#### F: Hur kan jag placera fotnoter och slutnoter i Aspose.Words?

 S: För att placera fotnoter och slutnoter i Aspose.Words måste du använda`FootnoteOptions` klass och`Position` fast egendom. Du kan ställa in den här egenskapen till vilket värde du vill, t.ex`BottomOfPage` (längst ner på sidan) eller`EndOfSection` (i slutet av avsnittet).

#### F: Är det möjligt att anpassa positionen för fotnoter och slutnoter för varje sida eller avsnitt i dokumentet?

S: Ja, det är möjligt att anpassa positionen för fotnoter och slutnoter för varje sida eller avsnitt i dokumentet. Du kan använda Aspose.Words sektions- och sidamanipulationsmetoder för att definiera specifika positioner för fotnoter och slutnoter.

#### F: Hur tar jag bort fotnoter eller slutnoter från ett dokument?

 S: För att ta bort fotnoter eller slutnoter från ett dokument i Aspose.Words kan du använda lämpliga metoder som t.ex.`RemoveAllFootnotes` för att ta bort alla fotnoter eller`RemoveAllEndnotes` för att ta bort alla slutnoter. Se till att spara dokumentet efter att du har utfört dessa operationer.

#### F: Kan fotnoter och slutnoter placeras utanför sidmarginalerna?

Nej, fotnoter och slutnoter kan som standard inte placeras utanför sidmarginalerna i Aspose.Words. Du kan dock justera dokumentmarginalerna för att ge mer utrymme för fotnoter och slutnoter om det behövs.

#### F: Kan fotnoter och slutnoter anpassas med specifika teckensnitt eller formateringsstilar?

S: Ja, du kan anpassa fotnoter och slutnoter med specifika teckensnitt eller formateringsstilar i Aspose.Words. Du kan använda de tillgängliga metoderna och egenskaperna för att tillämpa teckensnittsstilar, färger, teckenstorlekar, etc. fotnoter och slutnoter.