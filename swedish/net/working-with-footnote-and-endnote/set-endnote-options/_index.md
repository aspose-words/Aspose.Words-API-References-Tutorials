---
title: Ställ in slutnotsalternativ
linktitle: Ställ in slutnotsalternativ
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in slutnotalternativ i Word-dokument med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/working-with-footnote-and-endnote/set-endnote-options/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att ställa in slutnotalternativ i ett Word-dokument. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt källdokument:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Steg 2: Initiera DocumentBuilder-objektet

 Initiera sedan`DocumentBuilder` objekt för att utföra operationer på dokumentet:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Lägga till text och slutanteckning

 Använd`Write` metod för`DocumentBuilder` objekt för att lägga till text i dokumentet, och`InsertFootnote` metod för att infoga en slutnot:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Steg 4: Ställa in alternativ för slutnot

 Få tillgång till`EndnoteOptions` egenskapen för dokumentet för att ändra slutnotalternativ. I det här exemplet ställer vi in omstartsregeln för att starta om på varje sida och positionen till slutet av avsnittet:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Steg 5: Spara dokumentet

Slutligen, spara det ändrade dokumentet:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Det är allt! Du har framgångsrikt angett slutnotsalternativ i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för Set Endnote Options med Aspose.Words för .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.
