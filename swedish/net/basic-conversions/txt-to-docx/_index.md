---
title: Txt till Docx
linktitle: Txt till Docx
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar vanliga textfiler (Txt) till Word-dokument (Docx) med Aspose.Words för .NET. Steg-för-steg handledning med exempelkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/txt-to-docx/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera en vanlig textfil (Txt) till ett Word-dokument i Docx-format. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till din vanliga textfil:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Steg 2: Spara dokumentet i Docx-format

 Spara sedan dokumentet i Docx-formatet genom att anropa`Save` metod på`Document`objekt och ange sökvägen och filnamnet för det utgående Docx-dokumentet:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

Det är allt! Du har framgångsrikt konverterat en vanlig textfil (Txt) till ett Word-dokument i Docx-format med Aspose.Words för .NET.

### Exempel på källkod för Txt To Docx med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kodningen av textfilen detekteras automatiskt.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.