---
title: Asiatisk Typografi Linjebrytning Grupp I Word-dokument
linktitle: Asiatisk Typografi Linjebrytning Grupp I Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder asiatisk typografi radbrytningsgrupp i word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/asian-typography-line-break-group/
---
I den här handledningen kommer vi att visa dig hur du använder asiatisk typografi radbrytningsgrupp i Word-dokumentfunktionen med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa formateringsändringar.

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

## Slutsats

 I den här handledningen utforskade vi funktionen "Asian Typography Line Break Group" i Aspose.Words för .NET. Genom att konfigurera`FarEastLineBreakControl`, `WordWrap` , och`HangingPunctuation` egenskaper hos`ParagraphFormat`, kunde vi kontrollera radbrytningsbeteendet för asiatisk typografi i ett Word-dokument. Den här funktionen är användbar för att hantera asiatiska tecken och säkerställa korrekta radbrytningar och radbrytning i dokument med blandat språkinnehåll.

### FAQ's

#### F: Vad är funktionen "Asian Typography Line Break Group" i Aspose.Words för .NET?

S: Funktionen "Asiatisk typografilinjebrytningsgrupp" i Aspose.Words för .NET låter dig kontrollera radbrytningsbeteendet för asiatisk typografi i ett Word-dokument. Specifikt påverkar det hur linjer bryts och lindas när man hanterar asiatiska tecken i stycken.

#### F: Hur aktiverar jag "Asian Typography Line Break Group" i Aspose.Words för .NET?

 S: För att aktivera "Asian Typography Line Break Group" måste du konfigurera`FarEastLineBreakControl`, `WordWrap` , och`HangingPunctuation` egenskaper hos`ParagraphFormat` för de relevanta styckena i ditt dokument. Miljö`FarEastLineBreakControl` till`false` ser till att asiatiska tecken behandlas på samma sätt som latinska tecken när det gäller radbrytning.`WordWrap` satt till`true` möjliggör ordbrytning för asiatisk typografi, och`HangingPunctuation` satt till`false` förhindrar att skiljetecken hänger i asiatisk text.

#### F: Kan jag använda "Asian Typography Line Break Group" på specifika stycken i ett dokument?

S: Ja, du kan använda inställningarna för "Asiatisk typografilinjebrytningsgrupp" på specifika stycken i ett Word-dokument. I exempelkoden tillämpas inställningarna på det första stycket i dokumentet. Du kan justera koden för att rikta in andra stycken efter behov genom att komma åt dem via`Paragraphs` samling av relevant(a) avsnitt i dokumentet.