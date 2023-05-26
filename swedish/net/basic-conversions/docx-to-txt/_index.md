---
title: Docx till txt
linktitle: Docx till txt
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument från Docx till vanlig text (Txt) med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-txt/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera ett Word-dokument i Docx-format till vanlig text (Txt). Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt med sökvägen till ditt källdokument i Docx-format:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Steg 2: Spara dokumentet i Txt-format

 Spara sedan dokumentet i vanlig text (Txt)-format genom att anropa`Save` metod på`Document` objekt och ange sökvägen och filnamnet för det utgående Txt-dokumentet:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

Det är allt! Du har framgångsrikt konverterat ett Word-dokument i Docx-format till vanlig text (Txt) med Aspose.Words för .NET.

### Exempel på källkod för Docx To Txt med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.