---
title: Ändra asiatiskt styckeavstånd och indrag i Word-dokument
linktitle: Ändra asiatiskt styckeavstånd och indrag i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ändrar asiatiskt styckeavstånd och indrag i Word-dokument med Aspose.Words för .NET.
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

Vi kommer nu att ändra avstånden och indragen i första stycket i det asiatiska dokumentet. Här är hur:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Uppdatera ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Uppdatera ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Uppdatera ParagraphFormat.FirstLineIndent
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
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent kommer att uppdateras.
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent kommer att uppdateras.
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent kommer att uppdateras.
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore kommer att uppdateras
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter kommer att uppdateras

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Med den här koden kommer du att kunna ändra mellanrum och indrag i ett asiatiskt stycke med Aspose.Words för .NET.

## Slutsats

 I den här handledningen lärde vi oss hur man ändrar avstånd och indrag i ett asiatiskt stycke med Aspose.Words för .NET. Genom att ändra de relevanta egenskaperna för`ParagraphFormat`kan vi styra layouten och utseendet på asiatiska stycken i ett Word-dokument. Den här funktionen är användbar för att anpassa formateringen av text med asiatiska tecken och för att uppnå önskad visuell presentation i dokument med blandat språkinnehåll.

### FAQ's

#### F: Vad gör funktionen "Ändra asiatiska styckeavstånd och indrag" i Aspose.Words för .NET?

S: Funktionen "Ändra asiatiskt styckeavstånd och indrag" i Aspose.Words för .NET låter dig ändra egenskaperna för avstånd och indrag för ett asiatiskt stycke i ett Word-dokument. Du kan justera värdena för vänster och höger indrag, första radens indrag, mellanslag före och mellanslag efter värden för att styra styckets layout och utseende.

#### F: Hur ändrar jag mellanrum och indrag i ett asiatiskt stycke med Aspose.Words för .NET?

 S: För att ändra mellanrum och indrag i ett asiatiskt stycke måste du komma åt`ParagraphFormat` målstycket och ändra dess relevanta egenskaper. I exempelkoden som tillhandahålls kommer vi åt första stycket i dokumentet och ställer in`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , och`LineUnitAfter` egenskaper för att justera avstånd och indrag.

#### F: Kan jag tillämpa dessa ändringar på andra stycken i dokumentet?

 S: Ja, du kan tillämpa dessa ändringar på andra stycken i dokumentet genom att gå till respektive`ParagraphFormat` föremål. Exempelkoden är inriktad på det första stycket i dokumentet, men du kan ändra andra stycken genom att justera indexet i`Paragraphs` samling eller använda andra kriterier för att välja önskade stycken.