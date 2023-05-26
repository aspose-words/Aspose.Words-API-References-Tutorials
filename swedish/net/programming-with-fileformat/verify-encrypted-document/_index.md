---
title: Verifiera krypterade dokument
linktitle: Verifiera krypterade dokument
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att verifiera att ett dokument är krypterat med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-fileformat/verify-encrypted-document/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för krypterad dokumentverifiering med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du kontrollerar om ett dokument är krypterat.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Upptäck filformat

 Därefter använder vi`DetectFileFormat` metod för`FileFormatUtil` klass för att upptäcka filformatinformationen. I det här exemplet antar vi att det krypterade dokumentet heter "Encrypted.docx" och finns i den angivna dokumentkatalogen.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Steg 3: Kontrollera om dokumentet är krypterat

 Vi använder`IsEncrypted` egendom av`FileFormatInfo` objekt för att kontrollera om dokumentet är krypterat. Den här egenskapen återkommer`true` om dokumentet är krypterat, annars returneras det`false`. Vi visar resultatet i konsolen.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Det är allt ! Du har framgångsrikt kontrollerat om ett dokument är krypterat med Aspose.Words för .NET.

### Exempel på källkod för att verifiera krypterade dokument med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```
