---
title: Docx till Rtf
linktitle: Docx till Rtf
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument från Docx till RTF-format med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-rtf/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera ett Word-dokument i Docx-format till RTF. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Läsa dokumentet från Stream

Öppna först en ström för att läsa Docx-dokumentet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Steg 2: Ladda dokumentet

Ladda sedan dokumentet från strömmen:

```csharp
Document doc = new Document(stream);
```

## Steg 3: Stänga strömmen

Eftersom dokumentet laddas in i minnet kan du stänga strömmen:

```csharp
stream.Close();
```

## Steg 4: Utföra operationer på dokumentet

Vid det här laget kan du utföra alla önskade operationer på dokumentet.

## Steg 5: Spara dokumentet i RTF-format

För att spara dokumentet i RTF-format, spara det i en minnesström:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Steg 6: Spola tillbaka strömmen

Innan du skriver minnesströmmen till en fil, spola tillbaka dess position till noll:

```csharp
dstStream.Position = 0;
```

## Steg 7: Skriva strömmen till fil

Skriv slutligen minnesströmmen till en RTF-fil:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

Det är allt! Du har framgångsrikt konverterat ett Word-dokument i Docx-format till RTF med Aspose.Words för .NET.

### Exempel på källkod för Docx To Rtf med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Skrivskyddad åtkomst räcker för att Aspose.Words ska kunna ladda ett dokument.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//Du kan stänga streamen nu, den behövs inte längre eftersom dokumentet finns i minnet.
	stream.Close();

	// ... gör något med dokumentet.

	// Konvertera dokumentet till ett annat format och spara för att streama.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Spola tillbaka streampositionen till noll så att den är redo för nästa läsare.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.