---
title: Upptäck dokumentsignaturer
linktitle: Upptäck dokumentsignaturer
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att upptäcka digitala signaturer i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-fileformat/detect-document-signatures/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för identifiering av dokumentsignatur med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du upptäcker digitala signaturer i ett dokument.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Upptäck digitala signaturer

 Därefter använder vi`DetectFileFormat` metod för`FileFormatUtil` klass för att upptäcka filformatinformationen. I det här exemplet antar vi att dokumentet heter "Digitalt signerad.docx" och finns i den angivna dokumentkatalogen.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Steg 3: Sök efter digitala signaturer

 Vi kontrollerar om dokumentet innehåller digitala signaturer med hjälp av`HasDigitalSignature` egendom av`FileFormatInfo` objekt. Om digitala signaturer upptäcks visar vi ett meddelande som indikerar att signaturerna kommer att gå förlorade om dokumentet öppnas/sparas med Aspose.Words.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

Det är allt ! Du har framgångsrikt upptäckt digitala signaturer i ett dokument med Aspose.Words för .NET.

### Exempel på källkod för att upptäcka dokumentsignaturer med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
