---
title: Docx till Markdown
linktitle: Docx till Markdown
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument från Docx till Markdown-format med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-markdown/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera ett Word-dokument i Docx-format till Markdown. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera Document- och DocumentBuilder-objekten

 Initiera först`Document` objekt och`DocumentBuilder` objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Lägga till innehåll i dokumentet

 Använd sedan`DocumentBuilder` objekt för att lägga till innehåll i dokumentet. I det här exemplet kommer vi att lägga till ett enkelt textstycke med hjälp av`Writeln` metod:

```csharp
builder.Writeln("Some text!");
```

Lägg gärna till mer komplext innehåll som rubriker, tabeller, listor eller formatering efter behov.

## Steg 3: Spara dokumentet i Markdown-format

 För att spara dokumentet i Markdown-format, använd`Save` metod på`Document` objekt och ange sökvägen och filnamnet för utdatadokumentet. I det här exemplet kommer vi att spara det som`"BaseConversions.DocxToMarkdown.md"`:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");
```

Det är allt! Du har framgångsrikt konverterat ett Word-dokument i Docx-format till Markdown med Aspose.Words för .NET.

### Exempel på källkod för Docx To Markdown med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Some text!");

	doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");

```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.