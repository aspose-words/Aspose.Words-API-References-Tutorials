---
title: Kryssruta Typ Innehållskontroll
linktitle: Kryssruta Typ Innehållskontroll
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar en innehållskontroll av kryssrutatyp i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/check-box-type-content-control/
---

Den här handledningen förklarar hur man skapar en kryssrutatyp innehållskontroll i ett Word-dokument med Aspose.Words för .NET. Innehållskontroller för kryssrutor tillåter användare att markera eller avmarkera en kryssruta i dokumentet.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och att arbeta med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa en Document and DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder` att bygga dokumentets innehåll.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Lägg till en kryssrutatyp Innehållskontroll
 Skapa en`StructuredDocumentTag` med`SdtType.Checkbox` för att representera kryssrutan innehållskontroll. Specificera`MarkupLevel.Inline` för att placera den i texten.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Steg 4: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Exempel på källkod för Check Box Type Content Control med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Det är allt! Du har skapat en kryssrutatyp innehållskontroll i ditt Word-dokument med Aspose.Words för .NET.