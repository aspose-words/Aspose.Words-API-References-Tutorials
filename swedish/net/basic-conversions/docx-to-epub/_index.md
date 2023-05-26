---
title: Docx till Epub
linktitle: Docx till Epub
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument från Docx till Epub-format med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-epub/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera ett Word-dokument i Docx-format till Epub-format. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Först måste du initiera`Document` objekt genom att tillhandahålla sökvägen till ditt källdokument i Docx-format. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska katalogsökvägen där ditt dokument finns, och`"Document.docx"` med namnet på ditt källdokument. Här är kodavsnittet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Steg 2: Konvertera dokumentet till Epub-format

 Därefter kan du fortsätta med konverteringsprocessen. Ring`Save` metod på`Document` objekt och ange sökvägen och filnamnet för utdatadokumentet i Epub-format. I det här exemplet kommer vi att spara det som`"BaseConversions.DocxToEpub.epub"`. Här är kodavsnittet:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

Det är allt! Du har framgångsrikt konverterat ett Word-dokument i Docx-format till Epub-format med Aspose.Words för .NET.

### Exempel på källkod för Docx till Epub med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.