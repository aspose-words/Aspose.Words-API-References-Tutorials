---
title: Ställ in stil för innehållskontroll
linktitle: Ställ in stil för innehållskontroll
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in stilen för en innehållskontroll i ett Word-dokument med Aspose.Words för .NET, med konsekvent formatering.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/set-content-control-style/
---

Den här handledningen förklarar hur du ställer in stilen för en innehållskontroll i ett Word-dokument med Aspose.Words för .NET. Du kan använda fördefinierade eller anpassade stilar på innehållskontroller för konsekvent formatering.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet och hämta innehållskontrollen
 Ladda Word-dokumentet med hjälp av`Document`konstruktor, skickar sökvägen till dokumentet som en parameter. Hämta önskad innehållskontroll från dokumentet. I det här exemplet antar vi att innehållskontrollen är den första strukturerade dokumenttaggen i dokumentet.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Steg 3: Hämta stilen och tillämpa på innehållskontroll
 Hämta önskad stil från dokumentets stilsamling. I det här exemplet hämtar vi stilen "Citat" genom att använda`StyleIdentifier.Quote` . Tilldela sedan den hämtade stilen till`Style` egenskapen för den strukturerade dokumenttaggen.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Steg 4: Spara dokumentet
 Spara det ändrade dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Exempel på källkod för Set Content Control Style med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Det är allt! Du har framgångsrikt ställt in stilen för en innehållskontroll i ditt Word-dokument med Aspose.Words för .NET.