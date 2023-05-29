---
title: Ställ in fotnots- och slutnotposition
linktitle: Ställ in fotnots- och slutnotposition
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in positionen för fotnoter och slutnoter i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att ställa in fotnoters och slutnoters position i ett Word-dokument. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt källdokument:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Steg 2: Ställ in fotnots- och slutnotposition

 Gå sedan till`FootnoteOptions` och`EndnoteOptions`egenskaper för dokumentet för att ställa in positionen för fotnoter och slutnoter. I det här exemplet ställer vi in fotnoternas position under texten och positionen för slutnoter i slutet av avsnittet:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Steg 3: Spara dokumentet

Spara slutligen det ändrade dokumentet:

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
