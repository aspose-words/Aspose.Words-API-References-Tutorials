---
title: Docx till byte
linktitle: Docx till byte
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument från Docx till byte-array med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-byte/
---

denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera ett Word-dokument i Docx-format till en byte-array. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera MemoryStream

 Skapa först en instans av`MemoryStream` klass för att lagra det konverterade dokumentet som en byte-array:

```csharp
MemoryStream outStream = new MemoryStream();
```

## Steg 2: Spara dokumentet i MemoryStream

 Använd sedan`Save` metod för`Document` klass för att spara dokumentet till`MemoryStream` i Docx-format:

```csharp
doc.Save(outStream, SaveFormat.Docx);
```

## Steg 3: Konvertera MemoryStream till Byte Array

 För att konvertera`MemoryStream` som innehåller Docx-dokumentet till en byte-array, använd`ToArray` metod:

```csharp
byte[] docBytes = outStream.ToArray();
```

## Steg 4: Initiera MemoryStream från Byte Array

 Initiera nu en ny instans av`MemoryStream`med hjälp av byte-arrayen som erhölls i föregående steg:

```csharp
MemoryStream inStream = new MemoryStream(docBytes);
```

## Steg 5: Skapa dokument från MemoryStream

 Slutligen, skapa en ny`Document` objekt från`MemoryStream`:

```csharp
Document docFromBytes = new Document(inStream);
```

Det är allt! Du har framgångsrikt konverterat ett Word-dokument i Docx-format till en byte-array med Aspose.Words för .NET.

### Exempel på källkod för Docx To Byte med Aspose.Words för .NET

```csharp

	// MemoryStream outStream = new MemoryStream();
	doc.Save(outStream, SaveFormat.Docx);

	byte[] docBytes = outStream.ToArray();
	MemoryStream inStream = new MemoryStream(docBytes);

	Document docFromBytes = new Document(inStream);
	
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.