---
title: Ställ in fotnotskolumner
linktitle: Ställ in fotnotskolumner
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in antalet kolumner för fotnoter i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att ställa in antalet kolumner för fotnoter i ett Word-dokument. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt källdokument:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Steg 2: Ställa in fotnotskolumner

 Gå sedan till`FootnoteOptions`egenskapen för dokumentet och ställ in`Columns` egenskap för att ange antalet kolumner för fotnoter. I det här exemplet ställer vi in det på 3 kolumner:

```csharp
doc.FootnoteOptions.Columns = 3;
```

## Steg 3: Spara dokumentet

Spara slutligen det ändrade dokumentet:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Det är allt! Du har ställt in antalet kolumner för fotnoter i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för Ställ in fotnotskolumner med Aspose.Words för .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// Ange antalet kolumner som fotnotsområdet är formaterat med.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.