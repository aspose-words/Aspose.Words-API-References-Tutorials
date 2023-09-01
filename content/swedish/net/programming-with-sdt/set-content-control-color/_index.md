---
title: Ställ in innehållskontrollfärg
linktitle: Ställ in innehållskontrollfärg
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in färgen på en innehållskontroll i ett Word-dokument med Aspose.Words för .NET och anpassar dess utseende.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/set-content-control-color/
---

Denna handledning förklarar hur man ställer in färgen på en innehållskontroll i ett Word-dokument med Aspose.Words för .NET. Du kan anpassa utseendet på innehållskontroller genom att ändra deras färg.

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
 Ladda Word-dokumentet med hjälp av`Document` konstruktor, skickar sökvägen till dokumentet som en parameter. Hämta önskad innehållskontroll från dokumentet. I det här exemplet antar vi att innehållskontrollen är den första strukturerade dokumenttaggen i dokumentet.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Steg 3: Ställ in innehållskontrollfärgen
 Ställ in färgen på innehållskontrollen genom att tilldela en`Color` värde till`Color` egenskapen för den strukturerade dokumenttaggen. I det här exemplet ställer vi in färgen till röd.

```csharp
sdt.Color = Color.Red;
```

## Steg 4: Spara dokumentet
 Spara det ändrade dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Exempel på källkod för Set Content Control Color med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Det är allt! Du har framgångsrikt angett färgen på en innehållskontroll i ditt Word-dokument med Aspose.Words för .NET.