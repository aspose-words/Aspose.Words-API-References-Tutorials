---
title: Pdf till jpeg
linktitle: Pdf till jpeg
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar PDF-dokument till JPEG-bilder med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/pdf-to-jpeg/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera ett PDF-dokument till JPEG-bilder. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt PDF-dokument:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Steg 2: Spara dokumentet som Jpeg-bilder

 Spara sedan dokumentet som Jpeg-bilder genom att anropa`Save` metod på`Document` objekt och ange sökvägen och filnamnet för utdata Jpeg-bilder:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");
```

Det är allt! Du har framgångsrikt konverterat ett PDF-dokument till Jpeg-bilder med Aspose.Words för .NET.

### Exempel på källkod för Pdf till Jpeg med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");

```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.