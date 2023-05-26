---
title: Aktuellt tillstånd för kryssrutan
linktitle: Aktuellt tillstånd för kryssrutan
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du hämtar och ställer in det aktuella tillståndet för en innehållskontroll i en kryssruta i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/current-state-of-check-box/
---

Den här handledningen förklarar hur du hämtar och ställer in det aktuella tillståndet för en innehållskontroll i en kryssruta i ett Word-dokument med Aspose.Words för .NET. Du kan markera eller avmarkera kryssrutan baserat på dess nuvarande tillstånd.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och att arbeta med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet och hämta innehållskontrollen för kryssrutan
 Ladda Word-dokumentet med hjälp av`Document` konstruktor, skickar sökvägen till dokumentet som en parameter. Hämta sedan önskad kryssruta innehållskontroll från dokumentet. I det här exemplet antar vi att kryssrutan är den första strukturerade dokumenttaggen i dokumentet.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Steg 3: Markera eller avmarkera kryssrutan baserat på dess nuvarande tillstånd
 Kontrollera om den hämtade strukturerade dokumenttaggen är av typen`SdtType.Checkbox` . Om det är det, ställ in`Checked` innehållskontrollens egendom till`true` för att markera rutan. Annars kan du lämna det omarkerat.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Steg 4: Spara dokumentet
 Spara det ändrade dokumentet i den angivna katalogen med hjälp av`Save`metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Exempel på källkod för Current State Of Check Box med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Få den första innehållskontrollen från dokumentet.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Det är allt! Du har framgångsrikt hämtat och ställt in det aktuella tillståndet för en kryssruta innehållskontroll i ditt Word-dokument med Aspose.Words för .NET.