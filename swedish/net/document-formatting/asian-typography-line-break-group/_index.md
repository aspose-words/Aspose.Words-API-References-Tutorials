---
title: Asian Typography Line Break Group
linktitle: Asian Typography Line Break Group
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder asiatisk typografi radbrytningsgrupp med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/asian-typography-line-break-group/
---

I den här handledningen kommer vi att visa dig hur du använder funktionen Asian Typography radbrytningsgrupp med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa formateringsändringar.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för dina dokument och ladda dokumentet som innehåller den asiatiska typografin i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Steg 2: Inställning av asiatisk typografi

Vi kommer nu att konfigurera de asiatiska typografiinställningarna för det första stycket i dokumentet. Här är hur:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Exempel på källkod för Asian Typography Line Break Group med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Asian Typography Line Break Group med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Med denna kod kommer du att kunna tillämpa asiatisk typografi radbrytningsgrupp med Aspose.Words för .NET.

