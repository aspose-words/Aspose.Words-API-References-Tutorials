---
title: Ändra asiatiskt styckeavstånd och indrag
linktitle: Ändra asiatiskt styckeavstånd och indrag
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ändrar asiatiskt styckeavstånd och indrag med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

I den här handledningen kommer vi att gå igenom hur du ändrar mellanrum och indrag i ett asiatiskt stycke med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för dina dokument och ladda dokumentet som innehåller den asiatiska typografin i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Steg 2: Ändra styckeavstånd och indrag

Vi kommer nu att ändra avståndet och indragen i första stycket i det asiatiska dokumentet. Här är hur:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Uppdatera ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Uppdatera ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // Uppdatera ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Uppdatera ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Uppdatera ParagraphFormat.SpaceAfter
```

## Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Exempel på källkod för Ändra asiatiska styckeavstånd och indrag med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Redigera asiatiska styckeavstånd och indrag med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent kommer att uppdateras
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent kommer att uppdateras
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent kommer att uppdateras
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore kommer att uppdateras
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter kommer att uppdateras

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Med denna kod kommer du att kunna ändra mellanrum och indrag i ett asiatiskt stycke med Aspose.Words för .NET.

