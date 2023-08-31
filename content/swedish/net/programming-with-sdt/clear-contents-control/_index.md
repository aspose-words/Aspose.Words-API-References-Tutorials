---
title: Rensa innehållskontroll
linktitle: Rensa innehållskontroll
second_title: Aspose.Words Document Processing API
description: Lär dig hur du rensar innehållet i en kontroll i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/clear-contents-control/
---

Denna handledning visar hur man rensar innehållet i en SDT i ett Word-dokument med Aspose.Words för .NET. Rensa innehållet i en SDT tar bort all text eller underordnade noder inom innehållskontrollen.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet och hämta StructuredDocumentTag
 Ladda Word-dokumentet med hjälp av`Document` konstruktor, skickar sökvägen till dokumentet som en parameter. Hämta sedan önskad`StructuredDocumentTag` från dokumentet. I det här exemplet antar vi att SDT är den första underordnade noden i dokumentet.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Steg 3: Rensa innehållet i StructuredDocumentTag
 Rensa innehållet i SDT med hjälp av`Clear` metod. Detta tar bort all text eller underordnade noder inom innehållskontrollen.

```csharp
sdt.Clear();
```

## Steg 4: Spara dokumentet
 Spara det ändrade dokumentet med hjälp av`Save`metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Exempel på källkod för Clear Contents Control med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Det är allt! Du har framgångsrikt rensat innehållet i en StructuredDocumentTag i ditt Word-dokument med Aspose.Words för .NET.