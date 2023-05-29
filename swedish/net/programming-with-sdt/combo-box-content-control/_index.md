---
title: Combo Box Innehållskontroll
linktitle: Combo Box Innehållskontroll
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar en Combo Box Content Control i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/combo-box-content-control/
---

Denna handledning förklarar hur man skapar en Combo Box Content Control i ett Word-dokument med Aspose.Words för .NET. Innehållskontroller i kombinationsrutan låter användare välja ett objekt från en rullgardinslista.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och att arbeta med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett dokument och StructuredDocumentTag
 Skapa en ny instans av`Document` klass och a`StructuredDocumentTag` för att representera kombinationsrutans innehållskontroll. Specificera`SdtType.ComboBox` som typ och`MarkupLevel.Block` som uppmärkningsnivå för att skapa en kombinationsruta på blocknivå.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Steg 3: Lägg till objekt i kombinationsrutan
 Lägg till objekt i kombinationsrutan med hjälp av`ListItems` egendom av`StructuredDocumentTag` . Varje objekt representeras av en`SdtListItem` objekt, som tar en visningstext och ett värde. I det här exemplet lägger vi till tre objekt i kombinationsrutan.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Steg 4: Lägg till StructuredDocumentTag till dokumentet
 Lägg till kombinationsrutans innehållskontroll till dokumentets brödtext genom att använda`AppendChild` metoden för dokumentets första avsnitts kropp.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Steg 5: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Exempel på källkod för Combo Box Content Control med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Det är allt! Du har framgångsrikt skapat en Combo Box Content Control i ditt Word-dokument med Aspose.Words för .NET.